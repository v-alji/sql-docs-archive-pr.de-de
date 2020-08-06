---
title: Anzeigen von Datenpunktbezeichnungen außerhalb eines Kreisdiagramms (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 959b7574-cf43-470b-b592-4944d8a9948f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dd4f38f24d2729acacfa3520635b93d8af2e9433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721181"
---
# <a name="display-data-point-labels-outside-a-pie-chart-report-builder-and-ssrs"></a><span data-ttu-id="32a8f-102">Anzeigen von Datenpunktbezeichnungen außerhalb eines Kreisdiagramms (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="32a8f-102">Display Data Point Labels Outside a Pie Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="32a8f-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]wird die Kreisdiagrammkennzeichnung optimiert, um Bezeichnungen auf nur einigen Segmenten der Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="32a8f-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], pie chart labeling is optimized to display labels on only several slices of data.</span></span> <span data-ttu-id="32a8f-104">Die Bezeichnungen überschneiden sich möglicherweise, wenn das Kreisdiagramm zu viele Slices enthält.</span><span class="sxs-lookup"><span data-stu-id="32a8f-104">Labels may overlap if the pie chart contains too many slices.</span></span> <span data-ttu-id="32a8f-105">Eine Lösung besteht darin, die Bezeichnungen außerhalb des Kreisdiagramms anzuzeigen, wodurch möglicherweise mehr Platz für längere Datenbezeichnungen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="32a8f-105">One solution is to display the labels outside the pie chart, which may create more room for longer data labels.</span></span> <span data-ttu-id="32a8f-106">Wenn Sie feststellen, dass sich die Bezeichnungen immer noch überschneiden, können Sie mehr Platz schaffen, indem Sie 3D aktivieren.</span><span class="sxs-lookup"><span data-stu-id="32a8f-106">If you find that your labels still overlap, you can create more space for them by enabling 3D.</span></span> <span data-ttu-id="32a8f-107">Dadurch wird der Durchmesser des Kreisdiagramms reduziert und mehr Platz um das Diagramm herum verfügbar.</span><span class="sxs-lookup"><span data-stu-id="32a8f-107">This reduces the diameter of the pie chart, creating more space around the chart.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-display-data-point-labels-inside-a-pie-chart"></a><span data-ttu-id="32a8f-108">So zeigen Sie Datenpunktbezeichnungen innerhalb eines Kreisdiagramms an</span><span class="sxs-lookup"><span data-stu-id="32a8f-108">To display data point labels inside a pie chart</span></span>  
  
1.  <span data-ttu-id="32a8f-109">Fügen Sie dem Bericht ein Kreisdiagramm hinzu.</span><span class="sxs-lookup"><span data-stu-id="32a8f-109">Add a pie chart to your report.</span></span> <span data-ttu-id="32a8f-110">Weitere Informationen finden Sie unter [Hinzufügen eines Diagramms zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="32a8f-110">For more information, see [Add a Chart to a Report &#40;Report Builder and SSRS&#41;](add-a-chart-to-a-report-report-builder-and-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="32a8f-111">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf das Diagramm, und wählen Sie **Datenbezeichnungen anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="32a8f-111">On the design surface, right-click on the chart and select **Show Data Labels**.</span></span>  
  
### <a name="to-display-data-point-labels-outside-a-pie-chart"></a><span data-ttu-id="32a8f-112">So zeigen Sie Datenpunktbezeichnungen außerhalb eines Kreisdiagramms an</span><span class="sxs-lookup"><span data-stu-id="32a8f-112">To display data point labels outside a pie chart</span></span>  
  
1.  <span data-ttu-id="32a8f-113">Erstellen Sie ein Kreisdiagramm, und zeigen Sie die Datenbezeichnungen an.</span><span class="sxs-lookup"><span data-stu-id="32a8f-113">Create a pie chart and display the data labels.</span></span>  
  
2.  <span data-ttu-id="32a8f-114">Öffnen Sie den Bereich Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="32a8f-114">Open the Properties pane.</span></span>  
  
3.  <span data-ttu-id="32a8f-115">Klicken Sie auf der Entwurfsoberfläche auf das Kreisdiagramm, um die **Category** -Eigenschaften im Eigenschaftenbereich anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="32a8f-115">On the design surface, click on the pie itself to display the **Category** properties in the Properties pane.</span></span>  
  
4.  <span data-ttu-id="32a8f-116">Erweitern Sie den Knoten **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="32a8f-116">Expand the **CustomAttributes** node.</span></span> <span data-ttu-id="32a8f-117">Eine Liste der Attribute für das Kreisdiagramm wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="32a8f-117">A list of attributes for the pie chart is displayed.</span></span>  
  
5.  <span data-ttu-id="32a8f-118">Legen Sie die **PieLabelStyle** -Eigenschaft auf **Außen**fest.</span><span class="sxs-lookup"><span data-stu-id="32a8f-118">Set the **PieLabelStyle** property to **Outside**.</span></span>  
  
6.  <span data-ttu-id="32a8f-119">Legen Sie die- `PieLineColor` Eigenschaft auf **schwarz**fest.</span><span class="sxs-lookup"><span data-stu-id="32a8f-119">Set the `PieLineColor` property to **Black**.</span></span> <span data-ttu-id="32a8f-120">Die PieLineColor-Eigenschaft definiert Legendenzeilen für jede Datenpunktbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="32a8f-120">The PieLineColor property defines callout lines for each data point label.</span></span>  
  
### <a name="to-prevent-overlapping-labels-displayed-outside-a-pie-chart"></a><span data-ttu-id="32a8f-121">So verhindern Sie überlappende Bezeichnungen außerhalb eines Kreisdiagramms</span><span class="sxs-lookup"><span data-stu-id="32a8f-121">To prevent overlapping labels displayed outside a pie chart</span></span>  
  
1.  <span data-ttu-id="32a8f-122">Erstellen Sie ein Kreisdiagramm mit externen Bezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="32a8f-122">Create a pie chart with external labels.</span></span>  
  
2.  <span data-ttu-id="32a8f-123">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste außerhalb des Kreisdiagramms, aber in den Diagrammrahmen, und wählen Sie **Diagrammflächeneigenschaften**aus. Das Dialogfeld **Diagrammflächeneigenschaften** erscheint daraufhin.</span><span class="sxs-lookup"><span data-stu-id="32a8f-123">On the design surface, right-click outside the pie chart but inside the chart borders and select **Chart Area Properties**.The **Chart AreaProperties** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="32a8f-124">Wählen Sie auf der Registerkarte **3D-Optionen** die Option **3D aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="32a8f-124">On the **3D Options** tab, select **Enable 3D**.</span></span>  
  
4.  <span data-ttu-id="32a8f-125">Wenn das Diagramm mehr Platz für Bezeichnungen bieten, aber dennoch zweidimensional bleiben soll, legen Sie die Eigenschaften **Drehung** und **Neigung** auf **0**fest.</span><span class="sxs-lookup"><span data-stu-id="32a8f-125">If you want the chart to have more room for labels but still appear two-dimensional, set the **Rotation** and **Inclination** properties to **0**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32a8f-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="32a8f-126">See Also</span></span>  
 <span data-ttu-id="32a8f-127">[Kreisdiagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="32a8f-127">[Pie Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="32a8f-128">[Zusammenfassen von kleinen Slices in einem Kreisdiagramm (Berichts-Generator und SSRS)](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="32a8f-128">[Collect Small Slices on a Pie Chart &#40;Report Builder and SSRS&#41;](collect-small-slices-on-a-pie-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="32a8f-129">Anzeigen von Prozentwerten in einem Kreisdiagramm &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="32a8f-129">Display Percentage Values on a Pie Chart &#40;Report Builder and SSRS&#41;</span></span>](display-percentage-values-on-a-pie-chart-report-builder-and-ssrs.md)  
  
  
