---
title: Formatieren eines Diagramms (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10214"
- sql12.rtp.rptdesigner.calculatedseriesproperties.fill.f1
- sql12.rtp.rptdesigner.serieslabelproperties.fill.f1
- sql12.rtp.rptdesigner.legendproperties.fill.f1
- "10149"
- sql12.rtp.rptdesigner.seriesproperties.shadow.f1
- sql12.rtp.rptdesigner.seriesproperties.markers.f1
- "10255"
- sql12.rtp.rptdesigner.charttitleproperties.fill.f1
- "10154"
- "10170"
- "10173"
- sql12.rtp.rptdesigner.seriesproperties.fill.f1
- "10169"
- "10158"
- sql12.rtp.rptdesigner.chartareaproperties.fill.f1
- sql12.rtp.rptdesigner.charttitleproperties.shadow.f1
- "10246"
- "10150"
- sql12.rtp.rptdesigner.calculatedseriesproperties.borders.f1
- sql12.rtp.rptdesigner.chartproperties.fill.f1
- "10159"
- sql12.rtp.rptdesigner.majorgridlineproperties.gridlineoptions.f1
- "10160"
- sql12.rtp.rptdesigner.serieslabelproperties.font.f1
- "10182"
- "10163"
- "10164"
- "10253"
- "10216"
- "10171"
- "10257"
- sql12.rtp.rptdesigner.chartareaproperties.border.f1
- sql12.rtp.rptdesigner.calculatedseriesproperties.shadow.f1
- sql12.rtp.rptdesigner.chartproperties.border.f1
- sql12.rtp.rptdesigner.minorgridlineproperties.gridlineoptions.f1
- sql12.rtp.rptdesigner.chartareaproperties.shadow.f1
- sql12.rtp.rptdesigner.charttitleproperties.borders.f1
- sql12.rtp.rptdesigner.charttitleproperties.font.f1
- "10247"
ms.assetid: d3984300-c766-42f8-b7c4-863123d67c99
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af164d4db9b6439f0634d113652b95939827b0f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616384"
---
# <a name="formatting-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="72ecc-102">Formatieren eines Diagramms (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="72ecc-102">Formatting a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="72ecc-103">Nachdem Sie die Daten für das Diagramm definiert und die gewünschte Darstellung ausgewählt haben, können Sie das Diagramm formatieren. So können Sie die Gesamtdarstellung verbessern und wichtige Datenpunkte hervorheben.</span><span class="sxs-lookup"><span data-stu-id="72ecc-103">After you have defined the data for your chart and it is appearing the way you want, you can add formatting to improve the overall appearance and highlight key data points.</span></span> <span data-ttu-id="72ecc-104">Die meisten allgemeinen Formatierungsoptionen können im Dialogfeld Eigenschaften geändert werden. Zum Auswählen dieses Dialogfelds klicken Sie mit der rechten Maustaste auf ein Diagrammelement, und zeigen Sie das Kontextmenü an.</span><span class="sxs-lookup"><span data-stu-id="72ecc-104">The most common formatting options can be modified from the Properties dialog box that are found when you right-click a chart element to display its shortcut menu.</span></span> <span data-ttu-id="72ecc-105">Jedes Diagrammelement hat ein eigenes Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="72ecc-105">Each chart element has its own dialog box.</span></span> <span data-ttu-id="72ecc-106">Weitere Informationen zu Diagrammelementen finden Sie unter [Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="72ecc-106">For more information about chart elements, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="72ecc-107">Alle Eigenschaften, die sich auf das Diagramm beziehen, befinden sich im Bereich Eigenschaften. Viele dieser Eigenschaften können jedoch auch in einem Dialogfeld festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="72ecc-107">All properties that relate to the chart are located in the Properties pane, but many of these properties can also be set from a dialog box.</span></span> <span data-ttu-id="72ecc-108">Beim Formatieren der Reihen können Sie mit benutzerdefinierten Attributen reihenspezifische Eigenschaften angeben. Diese Attribute finden Sie in der Kategorie **CustomAttributes** der Eigenschaften im Bereich „Eigenschaften“.</span><span class="sxs-lookup"><span data-stu-id="72ecc-108">If you are formatting the series, you can specify series-specific properties using custom attributes, which can only be found in the **CustomAttributes** category of properties, located in the Properties pane.</span></span>  
  
 <span data-ttu-id="72ecc-109">Um das Diagramm mit einer minimalen Anzahl von Schritten wirksam zu formatieren, ändern Sie die Standardrahmenart, die Palette und das Zeichnungsformat.</span><span class="sxs-lookup"><span data-stu-id="72ecc-109">To effectively format the chart using a minimal number of steps, change the default border style, palette and drawing style.</span></span> <span data-ttu-id="72ecc-110">Diese drei Funktionen erzeugen die größte sichtbare Änderung im Diagramm.</span><span class="sxs-lookup"><span data-stu-id="72ecc-110">These three features produce the largest visible change on the chart.</span></span> <span data-ttu-id="72ecc-111">Zeichnungsformate sind nur auf Kreis-, Ring-, Balken- und Säulendiagramme anwendbar.</span><span class="sxs-lookup"><span data-stu-id="72ecc-111">Drawing styles are only applicable to pie, doughnut, bar and column charts.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="in-this-section"></a><span data-ttu-id="72ecc-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="72ecc-112">In This Section</span></span>  
 [<span data-ttu-id="72ecc-113">Formatieren von Reihenfarben in einem Diagramm &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72ecc-113">Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="72ecc-114">Beschreibt das Definieren von Farben mit einer Palette, das Definieren einer eigenen Farbpalette und das Definieren von Farben basierend auf einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="72ecc-114">Discusses how colors are defined using a palette, how you can define your own color palette, and how to define colors based on an expression.</span></span>  
  
 [<span data-ttu-id="72ecc-115">Formatieren von Achsenbezeichnungen in einem Diagramm &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72ecc-115">Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="72ecc-116">Beschreibt, wie Gitternetzlinien, Teilstriche und Titel angezeigt und Zahlen und Datumswerte auf der Achsenskala formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="72ecc-116">Discusses how to display gridlines, tick marks, and titles, and how to format numbers and dates on the axis scale.</span></span>  
  
 [<span data-ttu-id="72ecc-117">Formatieren der Legende in einem Diagramm &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72ecc-117">Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-legend-formatting-report-builder.md)  
 <span data-ttu-id="72ecc-118">Erläutert, wie Elemente in der Diagrammlegende neu sortiert und formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="72ecc-118">Discusses how to re-order and format items in the chart legend.</span></span>  
  
 [<span data-ttu-id="72ecc-119">Formatieren von Datenpunkten in einem Diagramm &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72ecc-119">Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;</span></span>](formatting-data-points-on-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="72ecc-120">Erläutert, wie Datenpunktbezeichnungen positioniert und Datenpunktmarker für jede Reihe im Diagramm formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="72ecc-120">Discusses how to position data point labels and format data point markers for every series on the chart.</span></span>  
  
 [<span data-ttu-id="72ecc-121">3D, Abschrägungen und andere Effekte in einem Diagramm &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72ecc-121">3D, Bevel, and Other Effects in a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-3d-bevel-and-other-report-builder.md)  
 <span data-ttu-id="72ecc-122">Erläutert verschiedene 3D-Effekte, die Sie auf ein Diagramm anwenden können.</span><span class="sxs-lookup"><span data-stu-id="72ecc-122">Discusses various 3D effects that you can apply to a chart.</span></span>  
  
 [<span data-ttu-id="72ecc-123">Hinzufügen eines Rahmens zu einem Diagramm &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="72ecc-123">Add a Border Frame to a Chart &#40;Report Builder and SSRS&#41;</span></span>](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md)  
 <span data-ttu-id="72ecc-124">Erläutert das Hinzufügen eines Rahmens zu einem Diagramm.</span><span class="sxs-lookup"><span data-stu-id="72ecc-124">Explains how to add a border frame to a chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72ecc-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="72ecc-125">See Also</span></span>  
 <span data-ttu-id="72ecc-126">[Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="72ecc-126">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="72ecc-127">[Hinzufügen eines Rahmens zu einem Diagramm (Berichts-Generator und SSRS)](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="72ecc-127">[Add a Border Frame to a Chart &#40;Report Builder and SSRS&#41;](add-a-border-frame-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="72ecc-128">[Definieren von Farben in einem Diagramm mit einer Palette (Berichts-Generator und SSRS)](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="72ecc-128">[Define Colors on a Chart Using a Palette &#40;Report Builder and SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="72ecc-129">Hinzufügen einer Abschrägung, Prägung und Struktur zu einem Diagramm (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="72ecc-129">Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-effects-add-bevel-emboss-or-texture-report-builder.md)  
  
  
