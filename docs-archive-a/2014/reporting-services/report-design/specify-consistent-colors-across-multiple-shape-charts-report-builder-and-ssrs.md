---
title: Geben Sie konsistente Farben für mehrere Form Diagramme an (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d52f68e9-2ba7-4bff-9053-4089e5164ab4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c2c89f0f8cda3b7d6ef6b2acbd0de66c87170357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608269"
---
# <a name="specify-consistent-colors-across-multiple-shape-charts-report-builder-and-ssrs"></a><span data-ttu-id="56c3e-102">Angeben von Farben, die für mehrere Formdiagramme konsistent sind (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="56c3e-102">Specify Consistent Colors across Multiple Shape Charts (Report Builder and SSRS)</span></span>
  <span data-ttu-id="56c3e-103">Bei anderen Diagrammen als Formdiagrammen wird eine neue Farbe anhand des Indexes von Reihen im Diagramm ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="56c3e-103">On non-shape charts, a new color is selected from the palette based on the index of series in the chart.</span></span> <span data-ttu-id="56c3e-104">Beispielsweise wird die erste Reihe im Diagramm der ersten Farbe in der Palette zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="56c3e-104">For example, the first series on your chart will be mapped to the first color in the palette.</span></span> <span data-ttu-id="56c3e-105">Formdiagramme weisen jedoch ein anderes Verhalten auf.</span><span class="sxs-lookup"><span data-stu-id="56c3e-105">However, this behavior differs for shape charts.</span></span> <span data-ttu-id="56c3e-106">Bei Formdiagrammen wird jede Farbe in der Palette einem Datenpunkt im Dataset zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="56c3e-106">On shape charts, each color in the palette is mapped to a data point in the dataset.</span></span> <span data-ttu-id="56c3e-107">Beispielsweise wird Datenpunkt 1 der ersten Farbe in der Palette zugeordnet, Datenpunkt 2 wird der zweiten Farbe in der Palette zugeordnet usw.</span><span class="sxs-lookup"><span data-stu-id="56c3e-107">For example, data point 1 is mapped to the first color in the palette, data point 2 is mapped to the second color palette and so on.</span></span>  
  
 <span data-ttu-id="56c3e-108">Wenn ein Datenpunkt keinen Wert aufweist, wird er nicht im Formdiagramm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="56c3e-108">If a data point has no value, it is omitted from display on a shape chart.</span></span> <span data-ttu-id="56c3e-109">Dies bedeutet, dass dem Datenpunkt keine Farbe zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="56c3e-109">This means that the data point is skipped from being colored.</span></span> <span data-ttu-id="56c3e-110">Wenn beispielsweise Punkt 2 den Wert 0 (null) aufweist, wird Punkt 1 der ersten Farbe in der Palette und Punkt 3 der zweiten Farbe in der Palette zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="56c3e-110">For example, if point 2 has a value of zero, point 1 will be mapped to the first color in the palette, and point 3 will be mapped to the second color in the palette.</span></span> <span data-ttu-id="56c3e-111">Dieses Prinzip weist den Vorteil auf, dass für leere Punkte im Dataset eines Kreisdiagramms nicht unnötigerweise eine Palettenfarbe verwendet wird, wenn die leeren Punkte nicht gezeichnet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="56c3e-111">This approach is useful because the empty points in the dataset of a pie chart do not unnecessarily use a palette color when the empty point does not need to be drawn.</span></span>  
  
 <span data-ttu-id="56c3e-112">Als Nebeneffekt werden möglicherweise in einem Bericht, in dem mehrere Kreisdiagramme angezeigt werden, in den Kreisdiagrammen unterschiedliche Farben für Datenpunkte angezeigt, die derselben Kategoriegruppe angehören.</span><span class="sxs-lookup"><span data-stu-id="56c3e-112">As a side effect, when multiple pie charts are displayed in a report, the pie charts may display different colors for data points that have the same category grouping.</span></span> <span data-ttu-id="56c3e-113">Um dieses Problem zu lösen, müssen Sie einzelne Farben definieren, die nicht einzelnen Datenwerten, sondern einer Kategoriegruppe zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="56c3e-113">To resolve this, you need to define individual colors that map to a category group instead of individual data values.</span></span> <span data-ttu-id="56c3e-114">Die Vorgehensweise hängt hierbei davon ab, ob die Formdiagramme Sparklines in einer Tabelle oder Matrix sind, oder ob sie Formdiagramme im Bericht selbst sind.</span><span class="sxs-lookup"><span data-stu-id="56c3e-114">How you do this depends on if the shape charts are sparklines in a table or matrix, or if they are shape charts in the report itself.</span></span>  
  
 <span data-ttu-id="56c3e-115">Die Legende ist mit der Reihe verknüpft. Daher wird jede Farbe, die Sie für die Reihe angeben, automatisch in der Legende angezeigt.</span><span class="sxs-lookup"><span data-stu-id="56c3e-115">The legend is connected to the series, so any color you specify for the series will automatically be shown on the legend.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-specify-consistent-colors-across-multiple-sparkline-shape-charts-in-a-table-or-matrix"></a><span data-ttu-id="56c3e-116">So legen Sie konsistente Farben für mehrere Sparkline-Formdiagramme in einer Tabelle oder einer Matrix fest</span><span class="sxs-lookup"><span data-stu-id="56c3e-116">To specify consistent colors across multiple sparkline shape charts in a table or matrix</span></span>  
  
1.  <span data-ttu-id="56c3e-117">Klicken Sie zum Anzeigen des Bereichs Diagrammdaten auf das Diagramm.</span><span class="sxs-lookup"><span data-stu-id="56c3e-117">Click the chart to display the Chart Data pane.</span></span>  
  
2.  <span data-ttu-id="56c3e-118">Klicken Sie im Bereich **Kategoriegruppen** mit der rechten Maustaste auf eine Kategorie, und klicken Sie dann auf **Kategoriegruppeneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="56c3e-118">In the **Category Groups** area, right-click a category and click **Category Group Properties**.</span></span>  
  
3.  <span data-ttu-id="56c3e-119">Klicken Sie auf der Registerkarte Allgemein im Feld **Gruppen synchronisieren in** auf den Namen der Kategorie, für die die Farben synchronisiert werden sollen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="56c3e-119">On the General tab, in the **Synchronize groups in** box, click the name of the category for which you would like to synchronize colors, and then click **OK**.</span></span>  
  
### <a name="to-specify-consistent-colors-across-multiple-shape-charts"></a><span data-ttu-id="56c3e-120">So geben Sie konsistente Farben für mehrere Formdiagramme an</span><span class="sxs-lookup"><span data-stu-id="56c3e-120">To specify consistent colors across multiple shape charts</span></span>  
  
1.  <span data-ttu-id="56c3e-121">Klicken Sie mit der rechten Maustaste außerhalb des Hauptteils des Berichts, und wählen Sie **Berichtseigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="56c3e-121">Right-click outside the body of the report, and select **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="56c3e-122">Geben Sie in **Code**den folgenden Code in das Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="56c3e-122">In **Code**, type the following code into the textbox.</span></span>  
  
    ```  
    Private colorPalette As String() = {"Color1", "Color2", "Color3"}  
    Private count As Integer = 0  
    Private mapping As New System.Collections.Hashtable()  
    Public Function GetColor(ByVal groupingValue As String) As String  
        If mapping.ContainsKey(groupingValue) Then  
            Return mapping(groupingValue)  
        End If  
        Dim c As String = colorPalette(count Mod colorPalette.Length)  
        count = count + 1  
        mapping.Add(groupingValue, c)  
        Return c  
    End Function  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="56c3e-123">Sie müssen die Zeichenfolgen "Color1", "Color2" usw. durch eigene Farben ersetzen.</span><span class="sxs-lookup"><span data-stu-id="56c3e-123">You will need to replace the "Color1" strings with your own colors.</span></span> <span data-ttu-id="56c3e-124">Sie können benannte Farben, z. B. "Red", verwenden, oder Sie können einen sechsstelligen Hexadezimalwert verwenden, der die Farbe darstellt, z. B. "#FFFFFF" für Schwarz.</span><span class="sxs-lookup"><span data-stu-id="56c3e-124">You can use named colors, for example "Red", or you can use six-digit hexadecimal value that represent the color, such as "#FFFFFF" for black.</span></span> <span data-ttu-id="56c3e-125">Wenn mehr als drei Farben definiert sind, müssen Sie das Array der Farben so erweitern, dass die Anzahl der Farben im Array mit der Anzahl von Punkten im Formdiagramm übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="56c3e-125">If you have more than three colors defined, you will need to extend the array of colors so that the number of colors in the array matches the number of points in your shape chart.</span></span> <span data-ttu-id="56c3e-126">Sie können dem Array neue Farben hinzufügen, indem Sie eine durch Trennzeichen getrennte Liste von Zeichenfolgenwerten angeben, die benannte Farben oder hexadezimale Darstellungen von Farben enthalten.</span><span class="sxs-lookup"><span data-stu-id="56c3e-126">You can add new colors to the array by specifying a comma-separated list of string values that contain named colors or hexadecimal representations of colors.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="56c3e-127">Klicken Sie mit der rechten Maustaste auf das Formdiagramm, und wählen Sie **Reiheneigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="56c3e-127">Right-click on the shape chart and select **Series Properties**.</span></span>  
  
5.  <span data-ttu-id="56c3e-128">Klicken Sie unter **Ausfüllen**auf die **Ausdrucksschaltfläche** (*fx*), um den Ausdruck für die Eigenschaft **Farbe** zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="56c3e-128">In **Fill**, click the **Expression** (*fx*) button to edit the expression for the **Color** property.</span></span>  
  
6.  <span data-ttu-id="56c3e-129">Geben Sie den folgenden Ausdruck ein, wobei "MyCategoryField" das Feld ist, das im Bereich **Kategoriegruppen** angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="56c3e-129">Type the following expression, where "MyCategoryField" is the field that is displayed in the **Category Groups** area:</span></span>  
  
    ```  
    =Code.GetColor(Fields!MyCategoryField)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="56c3e-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56c3e-130">See Also</span></span>  
 <span data-ttu-id="56c3e-131">[Formatieren von Reihenfarben in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="56c3e-131">[Formatting Series Colors on a Chart &#40;Report Builder and SSRS&#41;](formatting-series-colors-on-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="56c3e-132">[Hinzufügen einer Abschrägung, Prägung und Struktur zu einem Diagramm (Berichts-Generator und SSRS)](chart-effects-add-bevel-emboss-or-texture-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="56c3e-132">[Add Bevel, Emboss, and Texture Styles to a Chart &#40;Report Builder and SSRS&#41;](chart-effects-add-bevel-emboss-or-texture-report-builder.md) </span></span>  
 <span data-ttu-id="56c3e-133">[Definieren von Farben in einem Diagramm mit einer Palette (Berichts-Generator und SSRS)](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="56c3e-133">[Define Colors on a Chart Using a Palette &#40;Report Builder and SSRS&#41;](define-colors-on-a-chart-using-a-palette-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="56c3e-134">[Fügen Sie dem Diagramm &#40;Berichts-Generator und SSRS leere Punkte hinzu&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="56c3e-134">[Add Empty Points to the Chart &#40;Report Builder and SSRS&#41;](add-empty-points-to-a-chart-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="56c3e-135">[Formdiagramme (Berichts-Generator und SSRS)](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="56c3e-135">[Shape Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="56c3e-136">[Verknüpfen mehrerer Datenbereiche mit einem Dataset &#40;Berichts-Generator und SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="56c3e-136">[Linking Multiple Data Regions to the Same Dataset &#40;Report Builder and SSRS&#41;](linking-multiple-data-regions-to-the-same-dataset-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="56c3e-137">[Geschachtelte Datenbereiche &#40;Berichts-Generator und SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="56c3e-137">[Nested Data Regions &#40;Report Builder and SSRS&#41;](nested-data-regions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="56c3e-138">Sparklines und Datenbalken &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="56c3e-138">Sparklines and Data Bars &#40;Report Builder and SSRS&#41;</span></span>](sparklines-and-data-bars-report-builder-and-ssrs.md)  
  
  
