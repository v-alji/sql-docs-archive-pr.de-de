---
title: Hinzufügen einer Abschrägung, eines Reliefs und von Texturstilen zu einem Diagramm (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 737cfc80-b39e-497c-817b-b46693deb58f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 92c5d4af47b7889b9ba5ec421706848f8822075b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621370"
---
# <a name="add-bevel-emboss-and-texture-styles-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="b82ff-102">Hinzufügen einer Abschrägung, Prägung und Struktur zu einem Diagramm (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="b82ff-102">Add Bevel, Emboss, and Texture Styles to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b82ff-103">Bei bestimmten Diagrammtypen können Sie einen Zeichnungseffekt angeben, um die visuelle Wirkung des Diagramms zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="b82ff-103">When using certain chart types, you can specify a drawing effect to increase the visual impact of your chart.</span></span> <span data-ttu-id="b82ff-104">Diese Zeichnungseffekte werden nur für die Reihen des Diagramms übernommen.</span><span class="sxs-lookup"><span data-stu-id="b82ff-104">These drawing effects are only applied to the series of your chart.</span></span> <span data-ttu-id="b82ff-105">Sie haben keine Auswirkungen auf andere Diagrammelemente.</span><span class="sxs-lookup"><span data-stu-id="b82ff-105">They have no effect on any other chart element.</span></span>  
  
 <span data-ttu-id="b82ff-106">Wenn Sie eine Variante eines Kreis- oder Ringdiagramms verwenden, können Sie einen weichen Rand oder eine konkave Zeichnungsart angeben ähnlich wie Abschrägungs- oder Prägungseffekte für ein Bild.</span><span class="sxs-lookup"><span data-stu-id="b82ff-106">When you are using any variant of a pie or doughnut chart, you can specify a soft edge or concave drawing style, similar to bevel or emboss effects that can be applied to an image.</span></span>  
  
 <span data-ttu-id="b82ff-107">Bei Verwendung einer Variante eines Balken- oder Säulendiagramms können Sie Strukturarten wie Zylinder, Keil und Helligkeitsabstufungen auf einzelne Balken oder Säulen anwenden.</span><span class="sxs-lookup"><span data-stu-id="b82ff-107">When you are using any variant of a bar or column chart, you can apply texture styles, such as cylinder, wedge, and light-to-dark, to the individual bars or columns.</span></span>  
  
 <span data-ttu-id="b82ff-108">Zusätzlich zu diesen Zeichnungsarten können vielen Diagrammelementen Rahmen und Schatten hinzugefügt werden, um eine Illusion von Tiefe zu vermitteln.</span><span class="sxs-lookup"><span data-stu-id="b82ff-108">In addition to these drawing styles, you can add borders and shadows to many chart elements to give the illusion of depth.</span></span> <span data-ttu-id="b82ff-109">Weitere Informationen zu anderen Möglichkeiten, das Diagramm zu formatieren, finden Sie unter [Formatieren eines Diagramms &#40;Berichts-Generator und SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b82ff-109">For more information on other ways to format the chart, see [Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-bevel-or-emboss-styles-to-a-pie-or-doughnut-chart"></a><span data-ttu-id="b82ff-110">So fügen Sie Abschrägungs- und Prägungseffekte zu einem Kreis- oder Ringdiagramm hinzu</span><span class="sxs-lookup"><span data-stu-id="b82ff-110">To add bevel or emboss styles to a pie or doughnut chart</span></span>  
  
1.  <span data-ttu-id="b82ff-111">Wählen Sie auf der Registerkarte **Ansicht** die Option **Eigenschaften** aus, um den Eigenschaftenbereich zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b82ff-111">On the **View** tab, select **Properties** to open the Properties pane.</span></span>  
  
2.  <span data-ttu-id="b82ff-112">Wählen Sie das Kreis- oder Ringdiagramm aus, das Sie optimieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b82ff-112">Select the pie or doughnut chart that you want to enhance.</span></span> <span data-ttu-id="b82ff-113">Wählen Sie ein Datenfeld im Diagramm aus und nicht das gesamte Diagramm.</span><span class="sxs-lookup"><span data-stu-id="b82ff-113">Select a data field in the chart, not the entire chart.</span></span>  
  
3.  <span data-ttu-id="b82ff-114">Erweitern Sie im Bereich Eigenschaften den Knoten **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="b82ff-114">In the Properties pane, expand the **CustomAttributes** node.</span></span>  
  
4.  <span data-ttu-id="b82ff-115">Wählen Sie für PieDrawingStyle eine Art aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="b82ff-115">For PieDrawingStyle, select a style from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b82ff-116">Sie können 3D nicht mit Abschrägungen oder Prägungen im selben Diagramm verwenden.</span><span class="sxs-lookup"><span data-stu-id="b82ff-116">You can't have 3D and bevel or emboss styles on the same chart.</span></span> <span data-ttu-id="b82ff-117">Wenn Sie für das Diagramm 3D aktiviert haben, wird die PieDrawingStyle-Eigenschaft nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b82ff-117">If you have enabled 3D for the chart, you will not see the PieDrawingStyle property.</span></span>  
  
 <span data-ttu-id="b82ff-118">![Kreisdiagramm mit konkaver Zeichnungsart](../media/rs-piedrawingeffects-concave.gif "Kreisdiagramm mit konkaver Zeichnungsart")</span><span class="sxs-lookup"><span data-stu-id="b82ff-118">![Pie chart with concave drawing style](../media/rs-piedrawingeffects-concave.gif "Pie chart with concave drawing style")</span></span>  
  
### <a name="to-add-texture-styles-to-a-bar-or-column-chart"></a><span data-ttu-id="b82ff-119">So fügen Sie einem Balken- oder Säulendiagramm Strukturarten hinzu</span><span class="sxs-lookup"><span data-stu-id="b82ff-119">To add texture styles to a bar or column chart</span></span>  
  
1.  <span data-ttu-id="b82ff-120">Wählen Sie das Balken- oder Säulendiagramm aus, das Sie optimieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b82ff-120">Select the bar or column chart that you want to enhance.</span></span> <span data-ttu-id="b82ff-121">Wählen Sie ein Datenfeld im Diagramm aus und nicht das gesamte Diagramm.</span><span class="sxs-lookup"><span data-stu-id="b82ff-121">Select a data field in the chart, not the entire chart.</span></span>  
  
2.  <span data-ttu-id="b82ff-122">Öffnen Sie den Bereich Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="b82ff-122">Open the Properties pane.</span></span>  
  
3.  <span data-ttu-id="b82ff-123">Erweitern Sie den Knoten **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="b82ff-123">Expand the **CustomAttributes** node.</span></span>  
  
4.  <span data-ttu-id="b82ff-124">Wählen Sie für DrawingStyle eine Art aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="b82ff-124">For DrawingStyle, select a style from the drop-down list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b82ff-125">Sie können 3D nicht mit Abschrägungen oder Prägungen im selben Diagramm verwenden.</span><span class="sxs-lookup"><span data-stu-id="b82ff-125">You can't have 3D and bevel or emboss styles on the same chart.</span></span> <span data-ttu-id="b82ff-126">Wenn Sie für das Diagramm 3D aktiviert haben, wird die PieDrawingStyle-Eigenschaft nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b82ff-126">If you have enabled 3D for the chart, you will not see the PieDrawingStyle property.</span></span>  
  
 <span data-ttu-id="b82ff-127">![Balkendiagramm mit LightToDark-Zeichnungseffekt](../media/rs-bardrawingeffects-lighttodark.gif "Balkendiagramm mit LightToDark-Zeichnungseffekt")</span><span class="sxs-lookup"><span data-stu-id="b82ff-127">![Bar chart with LightToDark drawing effect](../media/rs-bardrawingeffects-lighttodark.gif "Bar chart with LightToDark drawing effect")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b82ff-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b82ff-128">See Also</span></span>  
 <span data-ttu-id="b82ff-129">[Balkendiagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b82ff-129">[Bar Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b82ff-130">[Säulendiagramme (Berichts-Generator und SSRS)](column-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b82ff-130">[Column Charts &#40;Report Builder and SSRS&#41;](column-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b82ff-131">[Kreisdiagramme &#40;Berichts-Generator und SSRS&#41;](pie-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b82ff-131">[Pie Charts &#40;Report Builder and SSRS&#41;](pie-charts-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="b82ff-132">Formatieren eines Diagramms &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b82ff-132">Formatting a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-a-chart-report-builder-and-ssrs.md)  
  
  
