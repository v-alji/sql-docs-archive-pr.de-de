---
title: Hinzufügen von 3D-Effekten zu einem Diagramm (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: ab9625d8-6557-4a4d-8123-eefa7c066ff5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f4fcd90452e32b760bc446ac5d085ed00520a2f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621373"
---
# <a name="add-3d-effects-to-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="068c4-102">Hinzufügen von 3D-Effekten zu einem Diagramm (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="068c4-102">Add 3D Effects to a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="068c4-103">Dreidimensionale (3D-)Effekte können verwendet werden, um Tiefe zu vermitteln und dem Diagramm eine optische Wirkung zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="068c4-103">Three-dimensional (3D) effects can be used to provide depth and add visual impact to your chart.</span></span> <span data-ttu-id="068c4-104">Wenn Sie beispielsweise in einem explodierten Kreisdiagramm ein bestimmtes Segment des Kreises hervorheben möchten, können Sie die Perspektive des Diagramms so drehen und ändern, dass den Benutzern dieses Segment zuerst ins Auge fällt.</span><span class="sxs-lookup"><span data-stu-id="068c4-104">For example, if you want to emphasize a particular slice of an exploded pie chart, you can rotate and change the perspective of the chart so that people notice that slice first.</span></span> <span data-ttu-id="068c4-105">Wenn 3D-Effekte auf das Diagramm angewendet werden, werden der Farbverlauf und alle Schraffurstile deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="068c4-105">When 3D effects are applied to your chart, all gradient colors and hatching styles are disabled.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-apply-3d-effects-to-a-range-area-line-scatter-or-polar-chart"></a><span data-ttu-id="068c4-106">So übernehmen Sie 3D-Effekte für ein Bereichs-, Flächen-, Linien-, Punkt- oder Polardiagramm</span><span class="sxs-lookup"><span data-stu-id="068c4-106">To apply 3D effects to a Range, Area, Line, Scatter or Polar chart</span></span>  
  
1.  <span data-ttu-id="068c4-107">Klicken Sie mit der rechten Maustaste in die Diagrammfläche, und wählen Sie **3D-Effekte**aus.</span><span class="sxs-lookup"><span data-stu-id="068c4-107">Right-click anywhere inside the chart area and select **3D Effects**.</span></span> <span data-ttu-id="068c4-108">Das Dialogfeld **Diagrammflächeneigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="068c4-108">The **Chart Area Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="068c4-109">Wählen Sie unter **3D-Optionen**die Option **3D aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="068c4-109">In **3D Options**, select the **Enable 3D** option.</span></span>  
  
3.  <span data-ttu-id="068c4-110">(Optional) Unter **3D-Optionen**können Sie eine Vielzahl von Eigenschaften festlegen, die sich auf 3D-Winkel- und Szenenoptionen beziehen.</span><span class="sxs-lookup"><span data-stu-id="068c4-110">(Optional) In **3D Options**, you can set a variety of properties relating to 3D angles and scene options.</span></span> <span data-ttu-id="068c4-111">Weitere Informationen zu diesen Eigenschaften finden Sie unter [3D, Abschrägungen und andere Effekte in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](chart-effects-3d-bevel-and-other-report-builder.md)aus.</span><span class="sxs-lookup"><span data-stu-id="068c4-111">For more information about these properties, see [3D, Bevel, and Other Effects in a Chart &#40;Report Builder and SSRS&#41;](chart-effects-3d-bevel-and-other-report-builder.md).</span></span>  
  
4.  <span data-ttu-id="068c4-112">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="068c4-112">Click **OK**.</span></span>  
  
### <a name="to-apply-3d-effects-to-a-funnel-chart"></a><span data-ttu-id="068c4-113">So wenden Sie 3D-Effekte auf ein Trichterdiagramm an</span><span class="sxs-lookup"><span data-stu-id="068c4-113">To apply 3D effects to a Funnel chart</span></span>  
  
1.  <span data-ttu-id="068c4-114">Klicken Sie mit der rechten Maustaste in die Diagrammfläche, und wählen Sie **3D-Effekte**aus.</span><span class="sxs-lookup"><span data-stu-id="068c4-114">Right-click anywhere inside the chart area and select **3D Effects**.</span></span> <span data-ttu-id="068c4-115">Das Dialogfeld **Diagrammflächeneigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="068c4-115">The **Chart Area Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="068c4-116">Wählen Sie unter **3D-Optionen**die Option **3D aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="068c4-116">In **3D Options**, select the **Enable 3D** option.</span></span> <span data-ttu-id="068c4-117">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="068c4-117">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="068c4-118">(Optional) Um die visuelle Darstellung des Trichterdiagramms anzupassen, wechseln Sie in den Bereich Eigenschaften, und ändern Sie die für das Trichterdiagramm spezifischen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="068c4-118">(Optional) To customize the funnel chart visual appearance, you can go to the Properties pane and change properties specific to the funnel chart.</span></span>  
  
    1.  <span data-ttu-id="068c4-119">Öffnen Sie den Bereich Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="068c4-119">Open the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="068c4-120">Klicken Sie auf der Entwurfsoberfläche auf das Trichterdiagramm.</span><span class="sxs-lookup"><span data-stu-id="068c4-120">On the design surface, click anywhere on the funnel.</span></span> <span data-ttu-id="068c4-121">Die Eigenschaften für die Reihen des Trichterdiagramms werden im Bereich Eigenschaften angezeigt.</span><span class="sxs-lookup"><span data-stu-id="068c4-121">The properties for the series of the funnel chart are displayed in the Properties pane.</span></span>  
  
    3.  <span data-ttu-id="068c4-122">Erweitern Sie im Abschnitt **Allgemein** den Knoten **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="068c4-122">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
    4.  <span data-ttu-id="068c4-123">Wählen Sie für die **Funnel3DDrawingStyle** -Eigenschaft aus, ob der Trichter rund oder quadratisch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="068c4-123">For the **Funnel3DDrawingStyle** property, select whether the funnel will be shown with as circular or square.</span></span>  
  
    5.  <span data-ttu-id="068c4-124">Legen Sie für die **Funnel3DRotationAngle** -Eigenschaft einen Wert zwischen -10 und 10 fest.</span><span class="sxs-lookup"><span data-stu-id="068c4-124">For the **Funnel3DRotationAngle** property, set a value between -10 and 10.</span></span> <span data-ttu-id="068c4-125">Mit diesem Wert wird der Neigungswinkel bestimmt, der für das 3D-Trichterdiagramm verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="068c4-125">This will determine the degree of tilt that will be displayed on the 3D funnel chart.</span></span>  
  
### <a name="to-apply-3d-effects-to-a-pie-chart"></a><span data-ttu-id="068c4-126">So wenden Sie 3D-Effekte auf ein Kreisdiagramm an</span><span class="sxs-lookup"><span data-stu-id="068c4-126">To apply 3D effects to a Pie chart</span></span>  
  
1.  <span data-ttu-id="068c4-127">Klicken Sie mit der rechten Maustaste in die Diagrammfläche, und wählen Sie 3D-Effekte aus.</span><span class="sxs-lookup"><span data-stu-id="068c4-127">Right-click anywhere inside the chart area and select 3D Effects.</span></span> <span data-ttu-id="068c4-128">Das Dialogfeld **Diagrammflächeneigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="068c4-128">The **Chart Area Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="068c4-129">Wählen Sie unter **3D-Optionen**die Option **3D aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="068c4-129">In **3D Options**, select the **Enable 3D** option.</span></span> <span data-ttu-id="068c4-130">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="068c4-130">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="068c4-131">(Optional) Geben Sie unter **Drehung**einen ganzzahligen Wert ein, der die horizontale Drehung des Kreisdiagramms darstellt.</span><span class="sxs-lookup"><span data-stu-id="068c4-131">(Optional) In **Rotation**, type an integer value that represents the horizontal rotation of the pie chart.</span></span>  
  
4.  <span data-ttu-id="068c4-132">(Optional) Geben Sie unter **Neigung**einen ganzzahligen Wert ein, der die vertikale Drehung des Kreisdiagramms darstellt.</span><span class="sxs-lookup"><span data-stu-id="068c4-132">(Optional) In **Inclination**, type an integer value that represents the vertical tilt rotation of the pie chart.</span></span>  
  
5.  <span data-ttu-id="068c4-133">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="068c4-133">Click **OK**.</span></span>  
  
### <a name="to-apply-3d-effects-to-a-bar-or-column-chart"></a><span data-ttu-id="068c4-134">So wenden Sie 3D-Effekte auf ein Balken- oder Säulendiagramm an</span><span class="sxs-lookup"><span data-stu-id="068c4-134">To apply 3D effects to a Bar or Column chart</span></span>  
  
1.  <span data-ttu-id="068c4-135">Klicken Sie mit der rechten Maustaste in die Diagrammfläche, und wählen Sie **3D-Effekte**aus.</span><span class="sxs-lookup"><span data-stu-id="068c4-135">Right-click anywhere inside the chart area and select **3D Effects**.</span></span> <span data-ttu-id="068c4-136">Das Dialogfeld **Diagrammflächeneigenschaften** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="068c4-136">The **Chart Area Properties** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="068c4-137">Wählen Sie die Option **3D aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="068c4-137">Select the **Enable 3D** option.</span></span> <span data-ttu-id="068c4-138">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="068c4-138">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="068c4-139">(Optional) Wählen Sie die Option **Reihengruppierung aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="068c4-139">(Optional) Select the **Enable series clustering** option.</span></span> <span data-ttu-id="068c4-140">Wenn das Diagramm mehrere Balken- oder Säulendiagrammreihen enthält, werden die Reihen mit dieser Option gruppiert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="068c4-140">If your chart contains multiple bar or column chart series, this option will display the series as clustered.</span></span> <span data-ttu-id="068c4-141">Standardmäßig werden mehrere Balken- oder Säulenreihen nebeneinander angezeigt.</span><span class="sxs-lookup"><span data-stu-id="068c4-141">By default, multiple bar or column series are shown side-by-side.</span></span>  
  
4.  <span data-ttu-id="068c4-142">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="068c4-142">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="068c4-143">(Optional) Um Zylindereffekte einem Balken- oder Säulendiagramm hinzuzufügen, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="068c4-143">(Optional) To add cylinder effects to a bar or column chart, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="068c4-144">Öffnen Sie den Bereich Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="068c4-144">Open the Properties pane.</span></span>  
  
    2.  <span data-ttu-id="068c4-145">Klicken Sie auf der Entwurfsoberfläche auf einen beliebigen Balken der Reihe.</span><span class="sxs-lookup"><span data-stu-id="068c4-145">On the design surface, click any of the bars in the series.</span></span> <span data-ttu-id="068c4-146">Die Eigenschaften für die Reihe werden im Bereich "Eigenschaften" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="068c4-146">The properties for the series are displayed in the Properties pane.</span></span>  
  
    3.  <span data-ttu-id="068c4-147">Erweitern Sie im Abschnitt **Allgemein** den Knoten **CustomAttributes** .</span><span class="sxs-lookup"><span data-stu-id="068c4-147">In the **General** section, expand the **CustomAttributes** node.</span></span>  
  
    4.  <span data-ttu-id="068c4-148">Geben Sie für die **DrawingStyle** -Eigenschaft den Wert **Zylinder** ein.</span><span class="sxs-lookup"><span data-stu-id="068c4-148">For the **DrawingStyle** property, specify the **Cylinder** value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="068c4-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="068c4-149">See Also</span></span>  
 <span data-ttu-id="068c4-150">[3D, Abschrägungen und andere Effekte in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](chart-effects-3d-bevel-and-other-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="068c4-150">[3D, Bevel, and Other Effects in a Chart &#40;Report Builder and SSRS&#41;](chart-effects-3d-bevel-and-other-report-builder.md) </span></span>  
 <span data-ttu-id="068c4-151">[Formatieren eines Diagramms &#40;Berichts-Generator und SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="068c4-151">[Formatting a Chart &#40;Report Builder and SSRS&#41;](formatting-a-chart-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="068c4-152">Diagramme &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="068c4-152">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
