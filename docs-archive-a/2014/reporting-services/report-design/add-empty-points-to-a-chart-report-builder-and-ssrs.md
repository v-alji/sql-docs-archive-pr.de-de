---
title: Hinzufügen von leeren Punkten zum Diagramm (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2b056119-439f-494f-83cf-ee0c05dc6487
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 53d891c58210bcd51cd4e49f2f9a691a7729c884
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722537"
---
# <a name="add-empty-points-to-the-chart-report-builder-and-ssrs"></a><span data-ttu-id="28f9e-102">Hinzufügen von leeren Punkten zum Diagramm (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="28f9e-102">Add Empty Points to the Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="28f9e-103">NULL-Werte werden im Diagramm als Leerzeichen oder Lücken zwischen Datenpunkten einer Reihe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="28f9e-103">Null values are shown on the chart as empty spaces or gaps between data points in a series.</span></span> <span data-ttu-id="28f9e-104">Leere Punkte sind Datenpunkte, die in den leeren Bereich eingefügt werden können, der von NULL-Werten erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="28f9e-104">Empty points are data points that can be inserted in the empty space created by null values.</span></span>  
  
 <span data-ttu-id="28f9e-105">Standardmäßig werden leere Punkte berechnet, indem der Durchschnitt der vorherigen und nächsten Datenpunkte herangezogen wird, die einen Wert enthalten.</span><span class="sxs-lookup"><span data-stu-id="28f9e-105">By default, empty points are calculated by taking the average of the previous and next data points that contain a value.</span></span> <span data-ttu-id="28f9e-106">Sie können dies so ändern, dass alle leeren Punkte am Nullpunkt eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="28f9e-106">You can change this so that all empty points are inserted at zero.</span></span>  
  
 <span data-ttu-id="28f9e-107">Weitere Informationen finden Sie unter [Leere und NULL-Datenpunkte in Diagrammen &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="28f9e-107">For more information, see [Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-empty-points-on-a-chart"></a><span data-ttu-id="28f9e-108">So geben Sie leere Punkte in einem Diagramm an</span><span class="sxs-lookup"><span data-stu-id="28f9e-108">To specify empty points on a chart</span></span>  
  
1.  <span data-ttu-id="28f9e-109">Öffnen Sie den Bereich Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="28f9e-109">Open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="28f9e-110">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf die Reihe, die NULL-Werte enthält.</span><span class="sxs-lookup"><span data-stu-id="28f9e-110">On the design surface, right-click the series that contains null values.</span></span> <span data-ttu-id="28f9e-111">Die Eigenschaften für die Reihe werden im Bereich "Eigenschaften" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="28f9e-111">The properties for the series are displayed in the Properties pane.</span></span>  
  
3.  <span data-ttu-id="28f9e-112">Erweitern Sie den Knoten **EmptyPoint** .</span><span class="sxs-lookup"><span data-stu-id="28f9e-112">Expand the **EmptyPoint** node.</span></span>  
  
4.  <span data-ttu-id="28f9e-113">Wählen Sie für die Color-Eigenschaft einen Farbwert aus.</span><span class="sxs-lookup"><span data-stu-id="28f9e-113">Select a color value for the Color property.</span></span>  
  
5.  <span data-ttu-id="28f9e-114">Erweitern Sie im Knoten **EmptyPoint** den Knoten Marker.</span><span class="sxs-lookup"><span data-stu-id="28f9e-114">In the **EmptyPoint** node, expand the Marker node.</span></span>  
  
6.  <span data-ttu-id="28f9e-115">Wählen Sie für die MarkerType-Eigenschaft einen Markertyp aus.</span><span class="sxs-lookup"><span data-stu-id="28f9e-115">Select a marker type for the MarkerType property.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="28f9e-116">Sie müssen einen Markertyp wählen, um leere Punkte einem Balken-, Säulen- oder Punktdiagramm hinzufügen zu können.</span><span class="sxs-lookup"><span data-stu-id="28f9e-116">You must select a marker type to add empty points to a bar, column or scatter chart.</span></span> <span data-ttu-id="28f9e-117">Bei Flächen-, Linien- und Netzdiagrammen ist das Wählen eines Markertyps optional, weil der leere Bereich bzw. die Lücke im Diagramm gefüllt wird, ohne dass ein Marker angegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="28f9e-117">However, for area, line and radar charts, selecting a marker type is optional because the chart fills in the empty space or gap without requiring a marker to be specified.</span></span>  
  
7.  <span data-ttu-id="28f9e-118">Legen Sie den Wert des leeren Punkts fest.</span><span class="sxs-lookup"><span data-stu-id="28f9e-118">Set the value of the empty point.</span></span>  
  
    1.  <span data-ttu-id="28f9e-119">Erweitern Sie im Bereich Eigenschaften den Knoten **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="28f9e-119">In the Properties pane, expand the **CustomAttributes** node.</span></span>  
  
    2.  <span data-ttu-id="28f9e-120">Legen Sie die EmptyPointValue-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="28f9e-120">Set the EmptyPointValue property.</span></span> <span data-ttu-id="28f9e-121">Um leere Punkte bei einem Mittelwert der vorherigen und der nächsten Datenpunkte einzufügen, wählen Sie **Mittelwert**.</span><span class="sxs-lookup"><span data-stu-id="28f9e-121">To insert empty points at an average of the previous and next data points, select **Average**.</span></span> <span data-ttu-id="28f9e-122">Um leere Punkte am Nullpunkt einzufügen, wählen Sie **Null**.</span><span class="sxs-lookup"><span data-stu-id="28f9e-122">To insert empty points at zero, select **Zero**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28f9e-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28f9e-123">See Also</span></span>  
 <span data-ttu-id="28f9e-124">[Hinzufügen von Datasetfiltern, Datenbereichsfiltern und Gruppenfiltern &#40;Berichts-Generator und SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="28f9e-124">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="28f9e-125">[Diagrammtypen &#40;Berichts-Generator und SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="28f9e-125">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="28f9e-126">[Hinzufügen von Skalierungsunterbrechungen zu einem Diagramm &#40;Berichts-Generator und SSRS&#41;](add-scale-breaks-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="28f9e-126">[Add Scale Breaks to a Chart &#40;Report Builder and SSRS&#41;](add-scale-breaks-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="28f9e-127">Diagramme &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="28f9e-127">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
