---
title: Hinzufügen eines Diagramms zu einem Bericht (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a6b595dc-f775-4a53-8554-74a0bf9335ec
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 789dd6cce10b0425833ea63f2f7941ea75970a25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608306"
---
# <a name="add-a-chart-to-a-report-report-builder-and-ssrs"></a><span data-ttu-id="5d82d-102">Hinzufügen eines Diagramms zu einem Bericht (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="5d82d-102">Add a Chart to a Report (Report Builder and SSRS)</span></span>
  <span data-ttu-id="5d82d-103">Wenn Sie Daten in einem visuellen Format zusammenfassen möchten, verwenden Sie den Diagrammdatenbereich.</span><span class="sxs-lookup"><span data-stu-id="5d82d-103">When you want to summarize data in a visual format, use a Chart data region.</span></span> <span data-ttu-id="5d82d-104">Es ist wichtig, einen geeigneten Diagrammtyp für die von Ihnen dargestellten Daten auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="5d82d-104">It is important to choose an appropriate chart type for the type of data that you are presenting.</span></span> <span data-ttu-id="5d82d-105">Durch den Diagrammtyp wird bestimmt, wie gut die Daten interpretiert werden können, wenn sie in Diagrammform umgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="5d82d-105">This affects how well the data can be interpreted when put in chart form.</span></span> <span data-ttu-id="5d82d-106">Weitere Informationen finden Sie unter [Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5d82d-106">For more information, see [Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="5d82d-107">Am einfachsten können Sie einen Diagrammdatenbereich einem Bericht hinzufügen, indem Sie den Assistenten Neues Diagramm ausführen.</span><span class="sxs-lookup"><span data-stu-id="5d82d-107">The simplest way to add a Chart data region to your report is to run the New Chart Wizard.</span></span> <span data-ttu-id="5d82d-108">Mit dem Assistenten können Sie Säulen-, Linien-, Balken- und Flächendiagramme erstellen.</span><span class="sxs-lookup"><span data-stu-id="5d82d-108">The wizard offers column, line, pie, bar, and area charts.</span></span> <span data-ttu-id="5d82d-109">Für diese und andere Diagrammtypen können Sie auch manuell ein Diagramm hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5d82d-109">For these and other chart types, you can also add a chart manually.</span></span>  
  
 <span data-ttu-id="5d82d-110">Nachdem Sie einen Diagrammdatenbereich der Entwurfsoberfläche hinzugefügt haben, können Sie Berichtsdataset-Felder für numerische und nicht numerische Daten in den Diagrammdatenbereich des Diagramms ziehen.</span><span class="sxs-lookup"><span data-stu-id="5d82d-110">After you add a Chart data region to the design surface, you can drag report dataset fields for numeric and non-numeric data to the Chart Data pane of the chart.</span></span> <span data-ttu-id="5d82d-111">Klicken Sie auf das Diagramm, um den Diagrammdatenbereich mit den drei Bereichen Reihengruppen, Kategoriegruppen und Werte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5d82d-111">Click the chart to display the Chart Data pane with its three areas: Series Groups, Category Groups, and Values.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-chart-to-a-report-by-using-the-chart-wizard"></a><span data-ttu-id="5d82d-112">So fügen Sie einem Bericht ein Diagramm mit dem Diagramm-Assistenten hinzu</span><span class="sxs-lookup"><span data-stu-id="5d82d-112">To add a chart to a report by using the Chart Wizard</span></span>  
  
1.  > [!NOTE]  
    >  <span data-ttu-id="5d82d-113">Der Diagramm-Assistent ist nur in Berichts-Generator verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5d82d-113">The Chart Wizard is only available in Report Builder.</span></span>  
  
     <span data-ttu-id="5d82d-114">Klicken Sie auf der Registerkarte **Einfügen** auf **Diagramm**und dann auf **Diagramm-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="5d82d-114">On the **Insert** tab, click **Chart**, and then click **Chart Wizard**.</span></span>  
  
2.  <span data-ttu-id="5d82d-115">Führen Sie die Schritte im Assistenten **Neues Diagramm** aus.</span><span class="sxs-lookup"><span data-stu-id="5d82d-115">Follow the steps in the **New** Chart wizard.</span></span>  
  
3.  <span data-ttu-id="5d82d-116">Klicken Sie auf der Registerkarte **Home** auf **Ausführen** , um den gerenderten Bericht anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5d82d-116">On the **Home** tab, click **Run** to see the rendered report.</span></span>  
  
4.  <span data-ttu-id="5d82d-117">Klicken Sie auf der Registerkarte **Ausführen** auf **Entwurf** , um den Bericht weiter zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="5d82d-117">On the **Run** tab, click **Design** to continue working on the report.</span></span>  
  
### <a name="to-add-a-chart-to-a-report"></a><span data-ttu-id="5d82d-118">So fügen Sie einem Bericht ein Diagramm hinzu</span><span class="sxs-lookup"><span data-stu-id="5d82d-118">To add a chart to a report</span></span>  
  
1.  <span data-ttu-id="5d82d-119">Erstellen Sie einen Bericht, und definieren Sie ein Dataset.</span><span class="sxs-lookup"><span data-stu-id="5d82d-119">Create a report and define a dataset.</span></span> <span data-ttu-id="5d82d-120">Weitere Informationen finden Sie unter [Hinzufügen von Daten zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](../report-data/report-datasets-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5d82d-120">For more information, see [Add Data to a Report &#40;Report Builder and SSRS&#41;](../report-data/report-datasets-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="5d82d-121">Klicken Sie auf der Registerkarte **Einfügen** auf **Diagramm**und dann auf **Diagramm einfügen**.</span><span class="sxs-lookup"><span data-stu-id="5d82d-121">On the **Insert** tab, click **Chart**, and then click **Insert Chart**.</span></span>  
  
3.  <span data-ttu-id="5d82d-122">Klicken Sie auf der Entwurfsoberfläche auf die Stelle, an der die obere linke Ecke des Diagramms positioniert werden soll, und ziehen Sie den Mauszeiger an die Stelle, an der die untere rechte Ecke des Diagramms positioniert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5d82d-122">Click on the design surface where you want the upper-left corner of the chart, and then drag to where you want the lower-right corner of the chart.</span></span>  
  
     <span data-ttu-id="5d82d-123">Das Dialogfeld **Diagrammtyp auswählen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5d82d-123">The **Select Chart Type** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="5d82d-124">Wählen Sie den Diagrammtyp aus, den Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="5d82d-124">Select the type of chart you want to add.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="5d82d-125">Klicken Sie zum Anzeigen des Bereichs **Diagrammdaten** auf das Diagramm.</span><span class="sxs-lookup"><span data-stu-id="5d82d-125">Click the chart to display the **Chart Data** pane.</span></span>  
  
6.  <span data-ttu-id="5d82d-126">Fügen Sie dem Bereich **Werte** mindestens ein Feld hinzu.</span><span class="sxs-lookup"><span data-stu-id="5d82d-126">Add one or more fields to the **Values** area.</span></span> <span data-ttu-id="5d82d-127">Diese Informationen werden auf der Wertachse dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5d82d-127">This information will be plotted on the value axis.</span></span>  
  
7.  <span data-ttu-id="5d82d-128">Fügen Sie dem Bereich **Kategoriegruppen** ein Gruppierungsfeld hinzu.</span><span class="sxs-lookup"><span data-stu-id="5d82d-128">Add a grouping field to the **Category Groups** area.</span></span> <span data-ttu-id="5d82d-129">Wenn Sie dem Bereich **Kategoriegruppen** dieses Feld hinzufügen, wird automatisch ein Gruppierungsfeld erstellt.</span><span class="sxs-lookup"><span data-stu-id="5d82d-129">When you add this field to the **Category Groups** area, a grouping field is automatically created for you.</span></span> <span data-ttu-id="5d82d-130">Jede Gruppe stellt einen Datenpunkt in der Reihe dar.</span><span class="sxs-lookup"><span data-stu-id="5d82d-130">Each group represents a data point in your series.</span></span>  
  
8.  <span data-ttu-id="5d82d-131">Klicken Sie mit der rechten Maustaste auf das Datenfeld, und klicken Sie anschließend auf **Reiheneigenschaften**, um die Daten nach Kategorie zusammenzufassen.</span><span class="sxs-lookup"><span data-stu-id="5d82d-131">To summarize the data by category, right-click the data field and click **Series Properties**.</span></span> <span data-ttu-id="5d82d-132">Wählen Sie im Feld **Kategorie** das Kategoriefeld in der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="5d82d-132">In the **Category** box, select the category field from the drop-down list.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
9. <span data-ttu-id="5d82d-133">Klicken Sie auf der Registerkarte **Home** auf **Ausführen** , um den gerenderten Bericht anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5d82d-133">On the **Home** tab, click **Run** to see the rendered report.</span></span>  
  
10. <span data-ttu-id="5d82d-134">Klicken Sie auf der Registerkarte **Ausführen** auf **Entwurf** , um den Bericht weiter zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="5d82d-134">On the **Run** tab, click **Design** to continue working on the report.</span></span>  
  
 <span data-ttu-id="5d82d-135">In Diagrammen mit Achsen, z. B. Balken- und Säulendiagrammen, zeigt die Kategorieachse möglicherweise nicht alle Kategoriebezeichnungen an.</span><span class="sxs-lookup"><span data-stu-id="5d82d-135">On charts with axes, such as bar and column charts, the category axis may not display all the category labels.</span></span> <span data-ttu-id="5d82d-136">Weitere Informationen zum Ändern der Achsenbezeichnungen finden Sie unter [Angeben eines Achsenintervalls (Berichts-Generator und SSRS)](specify-an-axis-interval-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5d82d-136">For more information about how to change the axis labels, see [Specify an Axis Interval &#40;Report Builder and SSRS&#41;](specify-an-axis-interval-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d82d-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5d82d-137">See Also</span></span>  
 <span data-ttu-id="5d82d-138">[Diagramme &#40;Berichts-Generator und SSRS&#41;](charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5d82d-138">[Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5d82d-139">[Diagrammtypen &#40;Berichts-Generator und SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5d82d-139">[Chart Types &#40;Report Builder and SSRS&#41;](chart-types-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5d82d-140">[Leere und NULL-Datenpunkte in Diagrammen (Berichts-Generator und SSRS)](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5d82d-140">[Empty and Null Data Points in Charts &#40;Report Builder and SSRS&#41;](empty-and-null-data-points-in-charts-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="5d82d-141">[Tutorial: Hinzufügen eines Balkendiagramms zu einem Bericht (Berichts-Generator)](https://go.microsoft.com/fwlink/?LinkId=198052) </span><span class="sxs-lookup"><span data-stu-id="5d82d-141">[Tutorial: Adding a Bar Chart to Your Report (Report Builder)](https://go.microsoft.com/fwlink/?LinkId=198052) </span></span>  
 <span data-ttu-id="5d82d-142">[Tutorial: Hinzufügen eines Balkendiagramms zu einem Bericht (Berichts-Designer)](https://go.microsoft.com/fwlink/?LinkId=198042) </span><span class="sxs-lookup"><span data-stu-id="5d82d-142">[Tutorial: Adding a Bar Chart to a Report (Report Designer)](https://go.microsoft.com/fwlink/?LinkId=198042) </span></span>  
 <span data-ttu-id="5d82d-143">[Tutorial: Hinzufügen eines Kreisdiagramms zu einem Bericht (Berichts-Generator)](https://go.microsoft.com/fwlink/?LinkId=198051) </span><span class="sxs-lookup"><span data-stu-id="5d82d-143">[Tutorial: Adding a Pie Chart to Your Report (Report Builder)](https://go.microsoft.com/fwlink/?LinkId=198051) </span></span>  
 [<span data-ttu-id="5d82d-144">Tutorial: Hinzufügen eines Kreisdiagramms zu einem Bericht (Berichts-Designer)</span><span class="sxs-lookup"><span data-stu-id="5d82d-144">Tutorial: Adding a Pie Chart to a Report (Report Designer)</span></span>](https://go.microsoft.com/fwlink/?LinkId=198041)  
  
  
