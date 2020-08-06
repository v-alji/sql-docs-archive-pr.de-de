---
title: Anzeigen von Prozentwerten in einem Kreisdiagramm (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: eb905fc1-5235-4773-a27e-b07be9318be5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2dee9017d34f2751b790b2e4928571160b597f1d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617734"
---
# <a name="display-percentage-values-on-a-pie-chart-report-builder-and-ssrs"></a><span data-ttu-id="05c08-102">Anzeigen von Prozentwerten in einem Kreisdiagramm (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="05c08-102">Display Percentage Values on a Pie Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="05c08-103">Standardmäßig werden Kategorien in der Legende angezeigt, um jeden Wert zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="05c08-103">By default, categories are shown in the legend to identify each value.</span></span> <span data-ttu-id="05c08-104">Wenn Sie das Kreisdiagramm mit Kategoriebezeichnungen versehen haben, möchten Sie möglicherweise Prozentsätze in der Legende anzeigen.</span><span class="sxs-lookup"><span data-stu-id="05c08-104">If you have labeled the pie chart using category labels, you may want show percentages in the legend.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-percentage-values-as-labels-on-a-pie-chart"></a><span data-ttu-id="05c08-105">So zeigen Sie Prozentwerte als Bezeichnungen in einem Kreisdiagramm an</span><span class="sxs-lookup"><span data-stu-id="05c08-105">To display percentage values as labels on a pie chart</span></span>  
  
1.  <span data-ttu-id="05c08-106">Fügen Sie dem Bericht ein Kreisdiagramm hinzu.</span><span class="sxs-lookup"><span data-stu-id="05c08-106">Add a pie chart to your report.</span></span> <span data-ttu-id="05c08-107">Weitere Informationen finden Sie unter [Hinzufügen eines Diagramms zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="05c08-107">For more information, see [Add a Chart to a Report &#40;Report Builder and SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="05c08-108">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf das Kreisdiagramm, und wählen Sie **Datenbezeichnungen anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="05c08-108">On the design surface, right-click on the pie and select **Show Data Labels**.</span></span> <span data-ttu-id="05c08-109">Die Datenbezeichnungen sollten innerhalb jedes Segments des Kreisdiagramms angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="05c08-109">The data labels should appear within each slice on the pie chart.</span></span>  
  
3.  <span data-ttu-id="05c08-110">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf die Bezeichnungen, und wählen Sie **Reihenbezeichnungseigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="05c08-110">On the design surface, right-click on the labels and select **Series Label Properties**.</span></span> <span data-ttu-id="05c08-111">Das Dialogfeld **Reihenbezeichnungseigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05c08-111">The **Series Label Properties** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="05c08-112">Geben Sie `#PERCENT` für die Option Bezeichnungs **Daten** ein.</span><span class="sxs-lookup"><span data-stu-id="05c08-112">Type `#PERCENT` for the **Label data** option.</span></span>  
  
5.  <span data-ttu-id="05c08-113">(Optional) Wenn Sie die Anzahl von Dezimalstellen in der Bezeichnung angeben möchten, geben Sie „#PERECENT{P*n*}“ an, wobei *n* die Anzahl der anzuzeigenden Dezimalstellen darstellt.</span><span class="sxs-lookup"><span data-stu-id="05c08-113">(Optional) To specify how many decimal places the label shows, type "#PERCENT{P*n*}" where *n* is the number of decimal places to display.</span></span> <span data-ttu-id="05c08-114">Geben Sie z. B. "#PERCENT{P0}" ein, um keine Dezimalstellen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="05c08-114">For example, to display no decimal places, type "#PERCENT{P0}".</span></span>  
  
### <a name="to-display-percentage-values-in-the-legend-of-a-pie-chart"></a><span data-ttu-id="05c08-115">So zeigen Sie Prozentwerte in der Legende eines Kreisdiagramms an</span><span class="sxs-lookup"><span data-stu-id="05c08-115">To display percentage values in the legend of a pie chart</span></span>  
  
1.  <span data-ttu-id="05c08-116">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf das Kreisdiagramm, und wählen Sie **Reiheneigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="05c08-116">On the design surface, right-click on the pie chart and select **Series Properties**.</span></span> <span data-ttu-id="05c08-117">Das Dialogfeld **Reiheneigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="05c08-117">The **Series Properties** dialog box displays.</span></span>  
  
2.  <span data-ttu-id="05c08-118">Geben **Legend**Sie in Legende `#PERCENT` für die Eigenschaft **benutzerdefinierter Legenden Text** ein.</span><span class="sxs-lookup"><span data-stu-id="05c08-118">In **Legend**, type `#PERCENT` for the **Custom legend text** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05c08-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="05c08-119">See Also</span></span>  
 <span data-ttu-id="05c08-120">[Kreis Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="05c08-120">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="05c08-121">[Formatieren der Legende in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](chart-legend-formatting-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="05c08-121">[Formatting the Legend on a Chart &#40;Report Builder and SSRS&#41;](chart-legend-formatting-report-builder.md) </span></span>  
 <span data-ttu-id="05c08-122">[Anzeigen von Datenpunkt Bezeichnungen außerhalb eines Kreis Diagramms &#40;Berichts-Generator und SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="05c08-122">[Display Data Point Labels Outside a Pie Chart &#40;Report Builder and SSRS&#41;](display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="05c08-123">Zusammenfassen von kleinen Slices in einem Kreisdiagramm &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="05c08-123">Collect Small Slices on a Pie Chart &#40;Report Builder and SSRS&#41;</span></span>](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md)  
  
  
