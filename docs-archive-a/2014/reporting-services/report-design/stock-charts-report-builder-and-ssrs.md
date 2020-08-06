---
title: Kursdiagramme (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f75ca11e-b7f5-4ac0-ba17-fe6f82742dad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a0f8c9c7dbc750bdb477f2ea1d96aa03f7ad022f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608262"
---
# <a name="stock-charts-report-builder-and-ssrs"></a><span data-ttu-id="c8433-102">Kursdiagramme (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="c8433-102">Stock Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c8433-103">Ein Kursdiagramm ist speziell für Finanz- oder wissenschaftliche Daten ausgelegt, bei denen bis zu vier Werte pro Datenpunkt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c8433-103">A stock chart is specifically designed for financial or scientific data that uses up to four values per data point.</span></span> <span data-ttu-id="c8433-104">Diese Werte werden an den Hoch-, Tief-, Anfangs- und Schlusswerten ausgerichtet, die zur Aufzeichnung von Finanzkursdaten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c8433-104">These values align with the high, low, open and close values that are used to plot financial stock data.</span></span> <span data-ttu-id="c8433-105">Dieser Diagrammtyp zeigt Anfangs- und Schlusswerte mit Markern, normalerweise Zeilen oder Dreiecke, an.</span><span class="sxs-lookup"><span data-stu-id="c8433-105">This chart type displays opening and closing values by using markers, which are typically lines or triangles.</span></span> <span data-ttu-id="c8433-106">Im folgenden Beispiel werden die Anfangswerte durch Marker auf der linken Seite angezeigt, und die Schlusswerte werden durch Marker auf der rechten Seite dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c8433-106">In the following example, the opening values are shown by the markers on the left, and the closing values are shown by the markers on the right.</span></span>  
  
 <span data-ttu-id="c8433-107">![Kursdiagramm](../media/rs-stockchart.gif "Kursdiagramm")</span><span class="sxs-lookup"><span data-stu-id="c8433-107">![Stock chart](../media/rs-stockchart.gif "Stock chart")</span></span>  
  
 <span data-ttu-id="c8433-108">Ein Beispiel eines Börsendiagramms ist als [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] Berichts-Generator-Beispielbericht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c8433-108">An example of a stock chart is available as a sample [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] Report Builder report.</span></span> <span data-ttu-id="c8433-109">Weitere Informationen zum Herunterladen des Beispielberichts und anderer Berichte finden Sie unter [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)][Beispielberichte zu Berichts-Generator und Berichts-Designer](https://go.microsoft.com/fwlink/?LinkId=198283).</span><span class="sxs-lookup"><span data-stu-id="c8433-109">For more information about downloading this sample report and others, see [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)][Report Builder and Report Designer sample reports](https://go.microsoft.com/fwlink/?LinkId=198283).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="variations"></a><span data-ttu-id="c8433-110">Abweichungen</span><span class="sxs-lookup"><span data-stu-id="c8433-110">Variations</span></span>  
  
-   <span data-ttu-id="c8433-111">**Kerze**.</span><span class="sxs-lookup"><span data-stu-id="c8433-111">**Candlestick**.</span></span> <span data-ttu-id="c8433-112">Das Kerzendiagramm ist eine spezielle Form des Kursdiagramms, in dem mithilfe von Kästchen der Unterschied zwischen Anfangs- und Schlusswerten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c8433-112">The candlestick chart is a specialized form of the stock chart, wherein boxes are used to show the range between the open and close values.</span></span> <span data-ttu-id="c8433-113">Wie das Kursdiagramm kann das Kerzendiagramm bis zu vier Werte pro Datenpunkt anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c8433-113">Like the stock chart, the candlestick chart can display up to four values per data point.</span></span>  
  
## <a name="data-considerations-for-stock-charts"></a><span data-ttu-id="c8433-114">Überlegungen zu Daten für ein Kursdiagramm</span><span class="sxs-lookup"><span data-stu-id="c8433-114">Data Considerations for Stock Charts</span></span>  
  
-   <span data-ttu-id="c8433-115">Bei der Darstellung vieler Kursdatenpunkte, wie bei einem Jahresaktienkurs, ist es schwierig, die einzelnen Anfangs-, Schluss-, Hoch- und Tiefwerte jedes Datenpunkts zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c8433-115">When presenting many stock data points, such as annual stock price trend, it is difficult to distinguish each open, close, high and low value of each data point.</span></span> <span data-ttu-id="c8433-116">Erwägen Sie in diesem Fall, ein Liniendiagramm anstelle eines Kursdiagramms zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c8433-116">In this scenario, consider using a line chart instead of a stock chart.</span></span>  
  
-   <span data-ttu-id="c8433-117">Wenn Achsenbezeichnungen generiert werden, fängt die Kennzeichnung normalerweise auf dem Nullpunkt an.</span><span class="sxs-lookup"><span data-stu-id="c8433-117">When axis labels are generated, labeling usually begins at zero.</span></span>  <span data-ttu-id="c8433-118">Im Allgemeinen fluktuieren Aktienkurse nicht so stark wie anderen Datasets.</span><span class="sxs-lookup"><span data-stu-id="c8433-118">In general, stock prices do not fluctuate to the same degree as other data sets.</span></span> <span data-ttu-id="c8433-119">Deshalb ist es eventuell sinnvoll, den Beginn der Achsenbezeichnungen auf dem Nullpunkt zu deaktivieren, um eine bessere Übersicht über Ihre Daten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c8433-119">For this reason, you may want to disable the axis labels from starting at zero, in order to get a better view of your data.</span></span> <span data-ttu-id="c8433-120">Legen sie hierzu im Dialogfeld **Achseneigenschaften** oder im Fenster **Eigenschaften** die Option **IncludeZero** auf false fest.</span><span class="sxs-lookup"><span data-stu-id="c8433-120">To do this, set **IncludeZero** to **false** in the **Axis Properties** dialog box or the Properties window.</span></span> <span data-ttu-id="c8433-121">Weitere Informationen zum Generieren von Achsenbezeichnungen in einem Diagramm finden Sie unter [Formatieren von Achsenbezeichnungen in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c8433-121">For more information about how the chart generates axis labels, see [Formatting Axis Labels on a Chart &#40;Report Builder and SSRS&#41;](formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="c8433-122">bietet viele berechnete Zellen zur Verwendung mit Kursdiagrammen, wie "Price Indicator", "Relative Strength Index", "MACD" usw.</span><span class="sxs-lookup"><span data-stu-id="c8433-122">provides many calculated formulas for use with stock charts, including Price Indicator, Relative Strength Index, MACD and more.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8433-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8433-123">See Also</span></span>  
 <span data-ttu-id="c8433-124">[Bereichs Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c8433-124">[Range Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c8433-125">[Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c8433-125">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="c8433-126">[Formatieren eines Diagramms &#40;Berichts-Generator und SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c8433-126">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c8433-127">Achseneigenschaften (Dialogfeld), Achsenoptionen (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="c8433-127">Axis Properties Dialog Box, Axis Options &#40;Report Builder and SSRS&#41;</span></span>](../axis-properties-dialog-box-axis-options-report-builder-and-ssrs.md)  
  
  
