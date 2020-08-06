---
title: Ändern des Texts eines Legendenelements (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 9e82fa34-17ed-494f-b25d-03dcc353a21f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0d0bb721aa0ff03a5211065111c98605cd86e971
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621365"
---
# <a name="change-the-text-of-a-legend-item-report-builder-and-ssrs"></a><span data-ttu-id="c41ef-102">Ändern des Texts eines Legendenelements (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="c41ef-102">Change the Text of a Legend Item (Report Builder and SSRS)</span></span>
  <span data-ttu-id="c41ef-103">Wenn Sie ein Feld im Wertebereich des Diagramms ablegen, wird automatisch ein Legendenelement mit dem Namen dieses Felds erstellt.</span><span class="sxs-lookup"><span data-stu-id="c41ef-103">When a field is placed in the Values area of the chart, a legend item is automatically generated that contains the name of this field.</span></span> <span data-ttu-id="c41ef-104">Alle Legendenelemente im Diagramm sind mit jeweils einer Reihe verknüpft, mit Ausnahme von Formdiagrammen, bei denen die Legende stattdessen mit einzelnen Datenpunkten verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="c41ef-104">Every legend item is connected to an individual series on the chart, with the exception of shape charts, where the legend is connected to individual data points instead of individual series.</span></span>  
  
 <span data-ttu-id="c41ef-105">In Formdiagrammen können Sie den Text eines Legendenelements so ändern, dass weitere Informationen zu den einzelnen Datenpunkten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c41ef-105">On shape charts, you can change the text of a legend item to show more information about the individual data points.</span></span> <span data-ttu-id="c41ef-106">Wenn beispielsweise die Werte der Datenpunkte in der Legende als Prozentsätze angezeigt werden sollen, können Sie ein Schlüsselwort wie `#PERCENT` angeben.</span><span class="sxs-lookup"><span data-stu-id="c41ef-106">For example, if you want to show the values of the data points as percentages in the legend, you can use a keyword such as `#PERCENT`.</span></span> <span data-ttu-id="c41ef-107">Sie können .NET Framework-Formatcodes in Verbindung mit Schlüsselwörtern anfügen, um numerische Formate und Datumsformate anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="c41ef-107">You can append .NET Framework format codes in conjunction with keywords to apply numeric and date formats.</span></span> <span data-ttu-id="c41ef-108">Weitere Informationen zu Schlüsselwörtern finden Sie unter [Formatieren von Datenpunkten in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c41ef-108">For more information about keywords, see [Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="c41ef-109">![Sharp-Diagramm](../media/sharpchart.png "Sharp-Diagramm")</span><span class="sxs-lookup"><span data-stu-id="c41ef-109">![Sharp Chart](../media/sharpchart.png "Sharp Chart")</span></span>  
  
 <span data-ttu-id="c41ef-110">In Nicht-Formdiagrammen können Sie den Text eines Legendenelements ändern.</span><span class="sxs-lookup"><span data-stu-id="c41ef-110">On non-shape charts, you can change the text of a legend item.</span></span> <span data-ttu-id="c41ef-111">Wenn eine Reihe beispielsweise den Namen "Reihe1" aufweist, können Sie diesen in einen aussagekräftigeren Namen wie "Umsatz für 2008" ändern.</span><span class="sxs-lookup"><span data-stu-id="c41ef-111">For example, if your series name is "Series1", you may want to change the text to something more descriptive like "Sales for 2008".</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-modify-the-text-that-appears-in-the-legend-on-a-shape-chart"></a><span data-ttu-id="c41ef-112">So ändern Sie den Text, der in der Legende eines Formdiagramms angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="c41ef-112">To modify the text that appears in the legend on a Shape chart</span></span>  
  
1.  <span data-ttu-id="c41ef-113">Klicken Sie mit der rechten Maustaste auf eine Reihe, oder klicken Sie mit der rechten Maustaste auf ein Feld im Bereich **Werte** , und wählen Sie die Option **Reiheneigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="c41ef-113">Right-click on a series, or right-click on a field in the **Values** area, and select **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="c41ef-114">Klicken Sie auf **Legende** , und geben Sie im Feld **Benutzerdefinierter Legendentext** ein Schlüsselwort ein.</span><span class="sxs-lookup"><span data-stu-id="c41ef-114">Click **Legend** and in the **Custom legend text** box, type a keyword.</span></span>  
  
 <span data-ttu-id="c41ef-115">In der folgenden Tabelle sind Beispiele für diagrammspezifische Schlüsselwörter aufgelistet, die für die Eigenschaft **Benutzerdefinierter Legendentext** verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c41ef-115">The following table provides examples of chart-specific keywords to use for the **Custom Legend Text** property.</span></span> <span data-ttu-id="c41ef-116">Weitere Informationen zu Schlüsselwörtern finden Sie unter [Formatieren von Datenpunkten in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c41ef-116">For more information about keywords, see [Formatting Data Points on a Chart &#40;Report Builder and SSRS&#41;](formatting-data-points-on-a-chart-report-builder-and-ssrs.md).</span></span>  
  
|<span data-ttu-id="c41ef-117">Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="c41ef-117">Keyword</span></span>|<span data-ttu-id="c41ef-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c41ef-118">Description</span></span>|<span data-ttu-id="c41ef-119">Beispiel für den in der Legende angezeigten Text</span><span class="sxs-lookup"><span data-stu-id="c41ef-119">Example of what appears as text in the legend</span></span>|  
|-------------|-----------------|---------------------------------------------------|  
|`#PERCENT{P1}`|<span data-ttu-id="c41ef-120">Zeigt den Prozentsatz des Gesamtwerts mit einer Dezimalstelle an.</span><span class="sxs-lookup"><span data-stu-id="c41ef-120">Displays the percentage of the total value to one decimal place.</span></span>|<span data-ttu-id="c41ef-121">85.0%</span><span class="sxs-lookup"><span data-stu-id="c41ef-121">85.0%</span></span>|  
|`#VALY`|<span data-ttu-id="c41ef-122">Zeigt den tatsächlichen numerischen Wert des Datenfelds an.</span><span class="sxs-lookup"><span data-stu-id="c41ef-122">Displays the actual numeric value of the data field.</span></span>|<span data-ttu-id="c41ef-123">17000</span><span class="sxs-lookup"><span data-stu-id="c41ef-123">17000</span></span>|  
|`#VALY{C2}`|<span data-ttu-id="c41ef-124">Zeigt den tatsächlichen numerischen Wert des Datenfelds als Währung mit zwei Dezimalstellen an.</span><span class="sxs-lookup"><span data-stu-id="c41ef-124">Displays the actual numeric value of the data field as a currency to two decimal places.</span></span>|<span data-ttu-id="c41ef-125">$17000.00</span><span class="sxs-lookup"><span data-stu-id="c41ef-125">$17000.00</span></span>|  
|`#AXISLABEL (#PERCENT{P0})`|<span data-ttu-id="c41ef-126">Zeigt die Textdarstellung des Kategoriefelds an, gefolgt von dem Prozentsatz, der in den einzelnen Kategorien im Diagramm angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c41ef-126">Displays the text representation of the category field, followed by the percentage that each category displays on the chart.</span></span>|<span data-ttu-id="c41ef-127">Michael Blythe (85 %)</span><span class="sxs-lookup"><span data-stu-id="c41ef-127">Michael Blythe (85%)</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="c41ef-128">Das Schlüsselwort #AXISLABEL kann nur dann zur Laufzeit ausgewertet werden, wenn im Bereich **Reihengruppen** kein Feld angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="c41ef-128">The #AXISLABEL keyword can only be evaluated at run time when there is not a field specified in the **Series Groups** area.</span></span>  
  
### <a name="to-modify-the-text-that-appears-in-the-legend-on-a-non-shape-chart"></a><span data-ttu-id="c41ef-129">So ändern Sie den Text, der in der Legende eines Nicht-Formdiagramms angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="c41ef-129">To modify the text that appears in the legend on a non-Shape chart</span></span>  
  
1.  <span data-ttu-id="c41ef-130">Klicken Sie mit der rechten Maustaste auf eine Reihe, oder klicken Sie mit der rechten Maustaste auf ein Feld im Bereich **Werte** , und wählen Sie die Option **Reiheneigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="c41ef-130">Right-click on a series, or right-click on a field in the **Values** area, and select **Series Properties**.</span></span>  
  
2.  <span data-ttu-id="c41ef-131">Klicken Sie auf **Legende** , und geben Sie im Feld **Benutzerdefinierter Legendentext** eine Legendenbezeichnung ein.</span><span class="sxs-lookup"><span data-stu-id="c41ef-131">Click **Legend** and in the **Custom legend text** box, type a legend label.</span></span> <span data-ttu-id="c41ef-132">Die Reihe wird mit dem Text aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c41ef-132">The series is updated with your text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c41ef-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c41ef-133">See Also</span></span>  
 <span data-ttu-id="c41ef-134">[Formatieren der Legende in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](chart-legend-formatting-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="c41ef-134">[Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;](chart-legend-formatting-report-builder.md) </span></span>  
 <span data-ttu-id="c41ef-135">[Formatieren von Reihenfarben in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c41ef-135">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c41ef-136">Ausblenden von Legendenelementen im Diagramm (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="c41ef-136">Hide Legend Items on the Chart &#40;Report Builder and SSRS&#41;</span></span>](chart-legend-hide-items-report-builder.md)  
  
  
