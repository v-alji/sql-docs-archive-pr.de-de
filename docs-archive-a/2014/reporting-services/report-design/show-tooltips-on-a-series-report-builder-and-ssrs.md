---
title: Anzeigen von QuickInfos für eine Reihe (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 4c9606ff-e1c3-4cf7-a4e7-bb16f1a9e8ab
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9113ec843b3b9255f380b17ee1ab6b360fa1f60d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621345"
---
# <a name="show-tooltips-on-a-series-report-builder-and-ssrs"></a><span data-ttu-id="597e1-102">Anzeigen von QuickInfos für eine Reihe (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="597e1-102">Show ToolTips on a Series (Report Builder and SSRS)</span></span>
  <span data-ttu-id="597e1-103">Sie können den einzelnen Datenpunkten in einem Diagramm QuickInfos hinzufügen, um Informationen zum Datenpunkt anzuzeigen, beispielsweise den Gruppennamen, den Wert des Datenpunkts oder den Prozentsatz des Datenpunkts in Bezug auf die Gesamtreihe, wenn Benutzer mit dem Cursor auf den Datenpunkt in einem gerenderten Bericht zeigen.</span><span class="sxs-lookup"><span data-stu-id="597e1-103">You can add a ToolTip to each data point on the series of a chart to display information related to the data point, such as the group name, the value of the data point, or the percentage of the data point relative to the series total when users hover over the data point in a rendered report.</span></span>  
  
 <span data-ttu-id="597e1-104">Einer berechneten Reihe können keine QuickInfos hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="597e1-104">You cannot add a ToolTip to a calculated series.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-a-tooltip-on-each-data-point"></a><span data-ttu-id="597e1-105">So geben Sie eine QuickInfo für die Datenpunkte an</span><span class="sxs-lookup"><span data-stu-id="597e1-105">To specify a ToolTip on each data point</span></span>  
  
1.  <span data-ttu-id="597e1-106">Klicken Sie mit der rechten Maustaste auf die Reihe, oder klicken Sie mit der rechten Maustaste auf das Feld im Bereich **Werte** , und klicken Sie auf **Reiheneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="597e1-106">Right-click on the series or right-click on the field in the **Values** area, and click **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="597e1-107">Klicken Sie auf **Reihendaten** , und geben Sie für die **ToolTip** -Eigenschaft eine Zeichenfolge oder einen Ausdruck ein.</span><span class="sxs-lookup"><span data-stu-id="597e1-107">Click **Series Data** and, for the **ToolTip** property, type in a string or expression.</span></span> <span data-ttu-id="597e1-108">Sie können alle diagrammspezifischen Schlüsselwörter zur Darstellung anderer Elemente im Diagramm verwenden.</span><span class="sxs-lookup"><span data-stu-id="597e1-108">You can use any chart-specific keyword to represent another element on the chart.</span></span> <span data-ttu-id="597e1-109">Weitere Informationen finden Sie unter [Formatieren von Datenpunkten in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="597e1-109">For more information, see [Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="597e1-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="597e1-110">See Also</span></span>  
 <span data-ttu-id="597e1-111">[Formatieren von Datenpunkten in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="597e1-111">[Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="597e1-112">[Ändern Sie den Text eines Legenden Elements &#40;Berichts-Generator und SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="597e1-112">[Change the Text of a Legend Item &#40;Report Builder and SSRS&#41;](chart-legend-change-item-text-report-builder.md) </span></span>  
 <span data-ttu-id="597e1-113">[Formatieren von Reihen Farben in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="597e1-113">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="597e1-114">Hinzufügen einer Drillthroughaktion für einen Bericht (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="597e1-114">Add a Drillthrough Action on a Report &#40;Report Builder and SSRS&#41;</span></span>](add-a-drillthrough-action-on-a-report-report-builder-and-ssrs.md)  
  
  
