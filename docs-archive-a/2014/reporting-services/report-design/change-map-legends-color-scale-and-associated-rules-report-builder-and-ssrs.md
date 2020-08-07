---
title: Ändern der Karten Legenden, Farbskala und zugeordneten Regeln (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.shared.maprulesdistribution.f1
- "10512"
- "10539"
- "10533"
- sql12.rtp.rptdesigner.mappointlayerproperties.typerules.f1
- "10534"
- sql12.rtp.rptdesigner.maplegendproperties.general.f1
- sql12.rtp.rptdesigner.mapdistancescaleproperties.general.f1
- "10516"
- sql12.rtp.rptdesigner.mapcolorscaleproperties.labels.f1
- sql12.rtp.rptdesigner.maplegendtitleproperties.general.f1
- "10514"
- sql12.rtp.rptdesigner.shared.mapruleslegend.f1
- sql12.rtp.rptdesigner.mapcolorscaleproperties.general.f1
- sql12.rtp.rptdesigner.shared.embeddedlabels.f1
- "10513"
- sql12.rtp.rptdesigner.mappointlayerproperties.sizerules.f1
- sql12.rtp.rptdesigner.mapcolorscaletitleproperties.general.f1
- "10510"
- "10509"
- "10540"
- "10517"
ms.assetid: a1d691b2-c5ae-420f-af60-b7c54a7385a4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 17220c12e672ce49d3c5b1023f2a00db04e7613e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615803"
---
# <a name="change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs"></a><span data-ttu-id="65b32-102">Ändern der Kartenlegenden, Farbskala und zugeordneten Regeln (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="65b32-102">Change Map Legends, Color Scale, and Associated Rules (Report Builder and SSRS)</span></span>
  <span data-ttu-id="65b32-103">Eine Karte kann Legenden, eine Farbskala und eine Entfernungsskala enthalten.</span><span class="sxs-lookup"><span data-stu-id="65b32-103">A map can contain map legends, a color scale, and a distance scale.</span></span> <span data-ttu-id="65b32-104">Diese Teile einer Karte erleichtern Benutzern die Interpretation der Datenvisualisierung auf der Karte.</span><span class="sxs-lookup"><span data-stu-id="65b32-104">These parts of a map help users interpret the data visualization on the map.</span></span>  
  
 <span data-ttu-id="65b32-105">Legenden enthalten die folgenden Teile einer Karte:</span><span class="sxs-lookup"><span data-stu-id="65b32-105">Legends include the following parts of a map:</span></span>  
  
-   <span data-ttu-id="65b32-106">**Kartenlegende:** Enthält Informationen zur Interpretation der analytischen Daten, durch die die Anzeige eines Kartenelements auf einer Kartenebene verändert wird.</span><span class="sxs-lookup"><span data-stu-id="65b32-106">**Map legend** Displays a guide to help interpret the analytical data that varies the display of a map elements on a map layer.</span></span> <span data-ttu-id="65b32-107">Eine Karte kann mehrere Legenden enthalten.</span><span class="sxs-lookup"><span data-stu-id="65b32-107">A map can have multiple legends.</span></span> <span data-ttu-id="65b32-108">Für jede Kartenebene geben Sie die zu verwendende Legende an.</span><span class="sxs-lookup"><span data-stu-id="65b32-108">For each map layer, you A specify which legend to use.</span></span> <span data-ttu-id="65b32-109">Eine Legende kann eine Anleitung für mehrere Kartenebenen enthalten.</span><span class="sxs-lookup"><span data-stu-id="65b32-109">A legend can provide a guide to more than one map layer.</span></span>  
  
-   <span data-ttu-id="65b32-110">**Farbskala:** Enthält Informationen zur Interpretation der Farben auf der Karte.</span><span class="sxs-lookup"><span data-stu-id="65b32-110">**Color scale** Displays a guide to help interpret colors on the map.</span></span> <span data-ttu-id="65b32-111">Eine Karte enthält eine Farbskala.</span><span class="sxs-lookup"><span data-stu-id="65b32-111">A map has one color scale.</span></span> <span data-ttu-id="65b32-112">Die Daten für die Farbskala können aus mehreren Ebenen stammen.</span><span class="sxs-lookup"><span data-stu-id="65b32-112">Multiple layers can provide the data for the color scale.</span></span>  
  
-   <span data-ttu-id="65b32-113">**Entfernungsskala:** Enthält Informationen zur Interpretation des Maßstabs der Karte.</span><span class="sxs-lookup"><span data-stu-id="65b32-113">**Distance scale** Displays a guide to help interpret the scale of the map.</span></span> <span data-ttu-id="65b32-114">Eine Karte enthält eine Entfernungsskala.</span><span class="sxs-lookup"><span data-stu-id="65b32-114">A map has one distance scale.</span></span> <span data-ttu-id="65b32-115">Der aktuelle Zoomwert des Kartenviewports bestimmt die Entfernungsskala.</span><span class="sxs-lookup"><span data-stu-id="65b32-115">The current map viewport zoom value determines the distance scale.</span></span>  
  
 <span data-ttu-id="65b32-116">![rs_MapElements](../media/rs-mapelements.gif "rs_MapElements")</span><span class="sxs-lookup"><span data-stu-id="65b32-116">![rs_MapElements](../media/rs-mapelements.gif "rs_MapElements")</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="to-change-the-position-of-a-legend-relative-to-the-viewport"></a><a name="Viewport"></a> <span data-ttu-id="65b32-117">So ändern Sie die Position einer Legende in Bezug zum Viewport</span><span class="sxs-lookup"><span data-stu-id="65b32-117">To change the position of a legend relative to the viewport</span></span>  
  
#### <a name="to-change-the-position-of-a-legend-relative-to-the-viewport"></a><span data-ttu-id="65b32-118">So ändern Sie die Position einer Legende in Bezug zum Viewport</span><span class="sxs-lookup"><span data-stu-id="65b32-118">To change the position of a legend relative to the viewport</span></span>  
  
1.  <span data-ttu-id="65b32-119">Klicken Sie in Designansicht mit der rechten Maustaste auf die Legende, und öffnen Sie die _\<report item->_ Seite **Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="65b32-119">In Design view, right-click the legend and open the _\<report item->_**Properties** page.</span></span>  
  
2.  <span data-ttu-id="65b32-120">Klicken Sie in **Position**auf den Ort, der angibt, wo die Legende relativ zum Viewport angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="65b32-120">In **Position**, click the location that specifies where to display the legend relative to the viewport.</span></span>  
  
3.  <span data-ttu-id="65b32-121">Um die Legende außerhalb des Viewports anzuzeigen, wählen **Sie \<report item> außerhalb von Viewport anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="65b32-121">To display the legend outside the viewport, select **Show \<report item> outside viewport**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
    > [!NOTE]  
    >  <span data-ttu-id="65b32-122">In der Vorschau werden die zu skalierenden Kartenlegenden und Farbskalen nur angezeigt, wenn es Ergebnisse von den Regeln gibt, die sich auf diese Legende beziehen.</span><span class="sxs-lookup"><span data-stu-id="65b32-122">In preview, map legends and the color scale appear only when there are results from the rules related to that legend.</span></span> <span data-ttu-id="65b32-123">Wenn keine anzuzeigenden Elemente vorhanden sind, wird die Legende nicht im gerenderten Bericht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="65b32-123">If there are no items to display, the legend does not appear in the rendered report.</span></span>  
  
  
  
##  <a name="to-change-the-layout-of-a-map-legend"></a><a name="MapLegend"></a> <span data-ttu-id="65b32-124">So ändern Sie das Layout einer Kartenlegende</span><span class="sxs-lookup"><span data-stu-id="65b32-124">To change the layout of a map legend</span></span>  
  
#### <a name="to-change-the-layout-of-a-map-legend"></a><span data-ttu-id="65b32-125">So ändern Sie das Layout einer Kartenlegende</span><span class="sxs-lookup"><span data-stu-id="65b32-125">To change the layout of a map legend</span></span>  
  
1.  <span data-ttu-id="65b32-126">Klicken Sie in der Entwurfsansicht mit der rechten Maustaste auf die Legende, und öffnen Sie die Seite **Legendeneigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="65b32-126">In Design view, right-click the legend and open the **Legend Properties** page.</span></span>  
  
2.  <span data-ttu-id="65b32-127">Klicken Sie in **Legendenlayout**auf das Tabellenlayout, das Sie für die Legende verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="65b32-127">In **Legend layout**, click the table layout that you want to use for the legend.</span></span> <span data-ttu-id="65b32-128">Wenn Sie auf andere Optionen klicken, wird das Layout auf der Entwurfsoberfläche geändert.</span><span class="sxs-lookup"><span data-stu-id="65b32-128">As you click different options, the layout on the design surface changes.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-show-or-hide-a-map-legend-title"></a><a name="MapLegendTitle"></a> <span data-ttu-id="65b32-129">So blenden Sie einen Kartenlegendentitel ein oder aus</span><span class="sxs-lookup"><span data-stu-id="65b32-129">To show or hide a map legend title</span></span>  
  
#### <a name="to-show-or-hide-a-map-legend-title"></a><span data-ttu-id="65b32-130">So blenden Sie einen Kartenlegendentitel ein oder aus</span><span class="sxs-lookup"><span data-stu-id="65b32-130">To show or hide a map legend title</span></span>  
  
-   <span data-ttu-id="65b32-131">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf die Kartenlegende, und klicken Sie anschließend auf **Legendentitel anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="65b32-131">Right-click the map legend on the design surface, and then click **Show Legend Title**.</span></span>  
  
  
  
##  <a name="to-show-or-hide-a-color-scale-title"></a><a name="ColorScaleTitle"></a> <span data-ttu-id="65b32-132">So blenden Sie einen Farbskalatitel ein oder aus</span><span class="sxs-lookup"><span data-stu-id="65b32-132">To show or hide a color scale title</span></span>  
  
#### <a name="to-show-or-hide-a-color-scale-title"></a><span data-ttu-id="65b32-133">So blenden Sie einen Farbskalatitel ein oder aus</span><span class="sxs-lookup"><span data-stu-id="65b32-133">To show or hide a color scale title</span></span>  
  
-   <span data-ttu-id="65b32-134">Klicken Sie auf der Entwurfsoberfläche mit der rechten Maustaste auf die Farbskala, und klicken Sie anschließend auf **Farbskalatitel anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="65b32-134">Right-click the color scale on the design surface, and then click **Show Color Scale Title**.</span></span>  
  
  
  
##  <a name="to-move-items-out-of-the-first-legend"></a><a name="MoveItems"></a> <span data-ttu-id="65b32-135">So verschieben Sie Elemente aus der ersten Legende</span><span class="sxs-lookup"><span data-stu-id="65b32-135">To move items out of the first legend</span></span>  
 <span data-ttu-id="65b32-136">Erstellen Sie beliebig viele weitere Legenden, aktualisieren Sie dann die Regeln für jede Kartenebene, und legen Sie fest, in welcher Legende die Regelergebnisse angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="65b32-136">Create as many additional legends as you need and then update the rules for each map layer specify which legend to display the rule results in.</span></span>  
  
#### <a name="to-create-a-new-legend"></a><span data-ttu-id="65b32-137">So erstellen Sie eine neue Legende</span><span class="sxs-lookup"><span data-stu-id="65b32-137">To create a new legend</span></span>  
  
-   <span data-ttu-id="65b32-138">Klicken Sie in der Entwurfsansicht mit der rechten Maustaste außerhalb des Viewports auf die Karte, und klicken Sie anschließend auf **Legende hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="65b32-138">In Design view, right-click the map outside the map viewport, and then click **Add Legend**.</span></span>  
  
     <span data-ttu-id="65b32-139">Eine neue Legende wird auf der Karte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="65b32-139">A new legend appears on the map.</span></span>  
  
#### <a name="to-display-rule-results-in-a-legend"></a><span data-ttu-id="65b32-140">So zeigen Sie Regelergebnisse in einer Legende an</span><span class="sxs-lookup"><span data-stu-id="65b32-140">To display rule results in a legend</span></span>  
  
1.  <span data-ttu-id="65b32-141">Klicken Sie in der Entwurfsansicht auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="65b32-141">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="65b32-142">Klicken Sie mit der rechten Maustaste auf die Ebene mit den gewünschten Daten, und klicken Sie dann auf _\<map element type\>_ **Farbregel**.</span><span class="sxs-lookup"><span data-stu-id="65b32-142">Right-click the layer that has the data that you want and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="65b32-143">Klicken Sie auf **Legende**.</span><span class="sxs-lookup"><span data-stu-id="65b32-143">Click **Legend**.</span></span>  
  
4.  <span data-ttu-id="65b32-144">Klicken Sie in der Dropdownliste **In dieser Legende anzeigen** auf den Namen der Legende, in der die Regelergebnisse angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="65b32-144">In the **Show in this legend** drop-down list, click the name of the legend to display the rule results in.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-a-template-style"></a><a name="TemplateStyle"></a> <span data-ttu-id="65b32-145">So verändern Sie Kartenelementfarben auf Grundlage eines Vorlagenstils</span><span class="sxs-lookup"><span data-stu-id="65b32-145">To vary map element colors based on a template style</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-a-template-style"></a><span data-ttu-id="65b32-146">So verändern Sie Kartenelementfarben auf Grundlage eines Vorlagenstils</span><span class="sxs-lookup"><span data-stu-id="65b32-146">To vary map element colors based on a template style</span></span>  
  
1.  <span data-ttu-id="65b32-147">Klicken Sie in der Entwurfsansicht auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="65b32-147">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="65b32-148">Klicken Sie mit der rechten Maustaste auf die Ebene mit den gewünschten Daten, und klicken Sie dann auf _\<map element type\>_ **Farbregel**.</span><span class="sxs-lookup"><span data-stu-id="65b32-148">Right-click the layer that has the data that you want and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="65b32-149">Klicken Sie auf **Vorlagenstil anwenden**.</span><span class="sxs-lookup"><span data-stu-id="65b32-149">Click **Apply template style**.</span></span>  
  
     <span data-ttu-id="65b32-150">Ein Vorlagenstil gibt eine Schrift, eine Rahmenart und eine Farbpalette an.</span><span class="sxs-lookup"><span data-stu-id="65b32-150">A template style specifies font, border style, and color palette.</span></span> <span data-ttu-id="65b32-151">Jedem Kartenelement wird eine andere Farbe von der Farbpalette für das Design, das im Karten-Assistenten oder Kartenebenen-Assistenten angegeben wurde, zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="65b32-151">Each map element is assigned a different color from the color palette for the theme that was specified in the Map Wizard or Map Layer Wizard.</span></span> <span data-ttu-id="65b32-152">Dies ist die einzige Option, die für Ebenen gilt, die keine analytischen Daten zugeordnet haben.</span><span class="sxs-lookup"><span data-stu-id="65b32-152">This is the only option that applies to layers that do not have associated analytical data.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-color-palette"></a><a name="ColorPalette"></a> <span data-ttu-id="65b32-153">So verändern Sie Kartenelementfarben auf Grundlage der Farbpalette</span><span class="sxs-lookup"><span data-stu-id="65b32-153">To vary map element colors based on color palette</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-color-palette"></a><span data-ttu-id="65b32-154">So verändern Sie Kartenelementfarben auf Grundlage der Farbpalette</span><span class="sxs-lookup"><span data-stu-id="65b32-154">To vary map element colors based on color palette</span></span>  
  
1.  <span data-ttu-id="65b32-155">Klicken Sie in der Entwurfsansicht auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="65b32-155">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="65b32-156">Klicken Sie mit der rechten Maustaste auf die Ebene mit den gewünschten Daten, und klicken Sie dann auf _\<map element type\>_ **Farbregel**.</span><span class="sxs-lookup"><span data-stu-id="65b32-156">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="65b32-157">Klicken Sie auf **Daten mithilfe der Farbpalette anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="65b32-157">Click **Visualize data by using color palette**.</span></span>  
  
     <span data-ttu-id="65b32-158">Diese Option verwendet eine integrierte oder benutzerdefinierte Palette, die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="65b32-158">This option uses a built-in or custom palette that you specify.</span></span> <span data-ttu-id="65b32-159">Auf Grundlage von verknüpften analytischen Daten wird jedem Kartenelement eine andere Farbe oder ein Schatten der Farbe auf der Palette zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="65b32-159">Based on related analytical data, each map element is assigned a different color or shade of color from the palette.</span></span>  
  
4.  <span data-ttu-id="65b32-160">Geben Sie in **Datenfeld**den Namen des Felds ein, das die analytischen Daten enthält, die Sie durch Farbe darstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="65b32-160">In **Data field**, type the name of the field that contains the analytical data that you want to visualize by color.</span></span>  
  
5.  <span data-ttu-id="65b32-161">Wählen Sie unter **Palette**den Namen der zu verwendenden Palette in der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="65b32-161">In **Palette**, from the drop-down list, select the name of the palette to use.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-color-ranges"></a><a name="ColorRanges"></a> <span data-ttu-id="65b32-162">So verändern Sie Kartenelementfarben auf Grundlage des Farbbereichs</span><span class="sxs-lookup"><span data-stu-id="65b32-162">To vary map element colors based on color ranges</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-color-ranges"></a><span data-ttu-id="65b32-163">So verändern Sie Kartenelementfarben auf Grundlage des Farbbereichs</span><span class="sxs-lookup"><span data-stu-id="65b32-163">To vary map element colors based on color ranges</span></span>  
  
1.  <span data-ttu-id="65b32-164">Klicken Sie in der Entwurfsansicht auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="65b32-164">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="65b32-165">Klicken Sie mit der rechten Maustaste auf die Ebene mit den gewünschten Daten, und klicken Sie dann auf _\<map element type\>_ **Farbregel**.</span><span class="sxs-lookup"><span data-stu-id="65b32-165">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="65b32-166">Klicken Sie auf **Daten mithilfe von Farbbereichen anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="65b32-166">Click **Visualize data by using color ranges**.</span></span>  
  
     <span data-ttu-id="65b32-167">Durch diese Option werden in Kombination mit den Start-, Mittel- und Endfarben, die Sie auf dieser Seite angeben, und den Optionen, die Sie auf der Seite **Verteilung** angeben, die verknüpften analytischen Daten in Bereiche unterteilt.</span><span class="sxs-lookup"><span data-stu-id="65b32-167">This option, combined with the start, middle, and end colors that you specify on this page and the options that you specify on the **Distribution** page, divide the related analytical data into ranges.</span></span> <span data-ttu-id="65b32-168">Der Berichtsprozessor weist jedem Kartenelement die entsprechende Farbe auf Grundlage der zugeordneten Daten und dem Bereich zu, in die es fällt.</span><span class="sxs-lookup"><span data-stu-id="65b32-168">The report processor assigns the appropriate color to each map element based on the its associated data and the range that it falls into.</span></span>  
  
4.  <span data-ttu-id="65b32-169">Geben Sie in **Datenfeld**den Namen des Felds ein, das die analytischen Daten enthält, die Sie durch Farbe darstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="65b32-169">In **Data field**, type the name of the field that contains the analytical data that you want to visualize by color.</span></span>  
  
5.  <span data-ttu-id="65b32-170">Geben Sie in **Startfarbe**die Farbe an, die für den niedrigsten Bereich verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="65b32-170">In **Start color**, specify the color to use for the lowest range.</span></span>  
  
6.  <span data-ttu-id="65b32-171">Geben Sie in **Mittelfarbe**die Farbe an, die für den mittleren Bereich verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="65b32-171">In **Middle color**, specify the color to use for the middle range.</span></span>  
  
7.  <span data-ttu-id="65b32-172">Geben Sie in **Endfarbe**die Farbe an, die für den höchsten Bereich verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="65b32-172">In **End color**, specify the color to use for the highest range.</span></span>  
  
8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-vary-map-element-colors-based-on-custom-colors"></a><a name="CustomColors"></a> <span data-ttu-id="65b32-173">So verändern Sie Kartenelementfarben auf Grundlage benutzerdefinierter Farben</span><span class="sxs-lookup"><span data-stu-id="65b32-173">To vary map element colors based on custom colors</span></span>  
  
#### <a name="to-vary-map-element-colors-based-on-custom-colors"></a><span data-ttu-id="65b32-174">So verändern Sie Kartenelementfarben auf Grundlage benutzerdefinierter Farben</span><span class="sxs-lookup"><span data-stu-id="65b32-174">To vary map element colors based on custom colors</span></span>  
  
1.  <span data-ttu-id="65b32-175">Klicken Sie in der Entwurfsansicht auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="65b32-175">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="65b32-176">Klicken Sie mit der rechten Maustaste auf die Ebene mit den gewünschten Daten, und klicken Sie dann auf _\<map element type\>_ **Farbregel**.</span><span class="sxs-lookup"><span data-stu-id="65b32-176">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="65b32-177">Klicken Sie auf **Daten mithilfe benutzerdefinierter Farben anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="65b32-177">Click **Visualize data by using custom colors**.</span></span>  
  
     <span data-ttu-id="65b32-178">Diese Option verwendet die Liste der Farben, die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="65b32-178">This option uses the list of colors that you specify.</span></span> <span data-ttu-id="65b32-179">Auf Grundlage von verknüpften analytischen Daten wird jedem Kartenelement eine Farbe aus der Liste zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="65b32-179">Based on related analytical data, each map element is assigned a color from the list.</span></span> <span data-ttu-id="65b32-180">Wenn es mehr Kartenelemente als Farben gibt, wird keine Farbe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="65b32-180">If there are more map elements than colors, no color is assigned.</span></span>  
  
4.  <span data-ttu-id="65b32-181">Geben Sie in **Datenfeld**den Namen des Felds ein, das die analytischen Daten enthält, die Sie durch Farbe darstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="65b32-181">In **Data field**, type the name of the field that contains the analytical data that you want to visualize by color.</span></span>  
  
5.  <span data-ttu-id="65b32-182">Klicken Sie unter **Benutzerdefinierte Farben**auf **Hinzufügen** , um jede benutzerdefinierte Farbe anzugeben.</span><span class="sxs-lookup"><span data-stu-id="65b32-182">In **Custom colors**, click **Add** to specify each custom color.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-set-distribution-options-for-a-legend"></a><a name="DistributionOptions"></a> <span data-ttu-id="65b32-183">So legen Sie Verteilungsoptionen für eine Legende fest</span><span class="sxs-lookup"><span data-stu-id="65b32-183">To set distribution options for a legend</span></span>  
  
#### <a name="to-set-distribution-options-for-a-legend"></a><span data-ttu-id="65b32-184">So legen Sie Verteilungsoptionen für eine Legende fest</span><span class="sxs-lookup"><span data-stu-id="65b32-184">To set distribution options for a legend</span></span>  
  
1.  <span data-ttu-id="65b32-185">Klicken Sie in der Entwurfsansicht auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="65b32-185">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="65b32-186">Klicken Sie mit der rechten Maustaste auf die Ebene mit den gewünschten Daten, und klicken Sie dann auf _\<map element type\>_ **Farbregel**.</span><span class="sxs-lookup"><span data-stu-id="65b32-186">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="65b32-187">Wählen Sie die Option **Daten mithilfe von visualisieren aus** \<rule type\> .</span><span class="sxs-lookup"><span data-stu-id="65b32-187">Select the **Visualize data by using** \<rule type\> option.</span></span> <span data-ttu-id="65b32-188">Um Verteilungsoptionen zu verwenden, müssen Sie Bereiche auf der Seite **Verteilung** auf Grundlage analytischer Daten erstellen, die der Ebene zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="65b32-188">To use distribution options, you must create ranges on the **Distribution** page based on analytical data that is associated with the layer.</span></span>  
  
4.  <span data-ttu-id="65b32-189">Klicken Sie auf **Verteilung**.</span><span class="sxs-lookup"><span data-stu-id="65b32-189">Click **Distribution**.</span></span>  
  
5.  <span data-ttu-id="65b32-190">Wählen Sie einen der folgenden Verteilungstypen aus:</span><span class="sxs-lookup"><span data-stu-id="65b32-190">Select one of the following distribution types:</span></span>  
  
    -   <span data-ttu-id="65b32-191">**EqualInterval**.</span><span class="sxs-lookup"><span data-stu-id="65b32-191">**EqualInterval**.</span></span> <span data-ttu-id="65b32-192">Gibt Bereiche an, die die Daten in gleiche Bereichsintervalle unterteilen.</span><span class="sxs-lookup"><span data-stu-id="65b32-192">Specifies ranges that divide the data into equal range intervals.</span></span>  
  
    -   <span data-ttu-id="65b32-193">**EqualDistribution**.</span><span class="sxs-lookup"><span data-stu-id="65b32-193">**EqualDistribution**.</span></span> <span data-ttu-id="65b32-194">Gibt Bereiche an, die diese Daten teilen, damit jeder Bereich eine gleiche Anzahl von Elementen hat.</span><span class="sxs-lookup"><span data-stu-id="65b32-194">Specifies ranges that divide that data so that each range has an equal number of items.</span></span>  
  
    -   <span data-ttu-id="65b32-195">**Optimal**.</span><span class="sxs-lookup"><span data-stu-id="65b32-195">**Optimal**.</span></span> <span data-ttu-id="65b32-196">Gibt Bereiche an, die automatisch die Verteilung zum Erstellen von ausgewogenen Unterbereichen anpassen.</span><span class="sxs-lookup"><span data-stu-id="65b32-196">Specifies ranges that automatically adjust distribution to create balanced subranges.</span></span>  
  
    -   <span data-ttu-id="65b32-197">**Benutzerdefiniert**:</span><span class="sxs-lookup"><span data-stu-id="65b32-197">**Custom**.</span></span> <span data-ttu-id="65b32-198">Geben Sie Ihre eigene Anzahl von Bereichen an, um die Verteilung von Werten zu steuern.</span><span class="sxs-lookup"><span data-stu-id="65b32-198">Specify your own number of ranges to control the distribution of values.</span></span>  
  
     <span data-ttu-id="65b32-199">Weitere Informationen zu Verteilungsoptionen finden Sie unter [Unterschiedliche Polygon-, Linien- und Punktanzeigen bei der Verwendung von Regeln und analytischen Daten (Berichts-Generator und SSRS)](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span><span class="sxs-lookup"><span data-stu-id="65b32-199">For more information about distribution options, see [Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span></span>  
  
6.  <span data-ttu-id="65b32-200">Geben Sie in **Anzahl der Unterbereiche**die gewünschte Anzahl von Unterbereichen ein.</span><span class="sxs-lookup"><span data-stu-id="65b32-200">In **Number of subranges**, type the number of subranges to use.</span></span> <span data-ttu-id="65b32-201">Beim Verteilungstyp **Optimal**wird die Anzahl von Unterbereichen automatisch berechnet.</span><span class="sxs-lookup"><span data-stu-id="65b32-201">When the distribution type is **Optimal**, the number of subranges is automatically calculated.</span></span>  
  
7.  <span data-ttu-id="65b32-202">Geben Sie in **Bereichsanfang**einen minimalen Bereichswert ein.</span><span class="sxs-lookup"><span data-stu-id="65b32-202">In **Range start**, type a minimum range value.</span></span> <span data-ttu-id="65b32-203">Alle Werte die kleiner als die Anzahl sind, sind die gleichen im Bereichsminimum.</span><span class="sxs-lookup"><span data-stu-id="65b32-203">All values less than this number are the same as the range minimum.</span></span>  
  
8.  <span data-ttu-id="65b32-204">Geben Sie in **Bereichsende**einen maximalen Bereichswert ein.</span><span class="sxs-lookup"><span data-stu-id="65b32-204">In **Range end**, type a maximum range value.</span></span> <span data-ttu-id="65b32-205">Alle Werte die größer als diese Zahl sind, entsprechen dem Bereichsmaximum.</span><span class="sxs-lookup"><span data-stu-id="65b32-205">All values larger than this number are the same as the range maximum.</span></span>  
  
9. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-change-the-contents-of-a-rule-legend"></a><a name="RuleLegend"></a> <span data-ttu-id="65b32-206">So ändern Sie den Inhalt einer Regellegende</span><span class="sxs-lookup"><span data-stu-id="65b32-206">To change the contents of a rule legend</span></span>  
  
#### <a name="to-change-the-contents-of-a-color-size-width-or-marker-type-legend"></a><span data-ttu-id="65b32-207">So ändern Sie den Inhalt einer Farb-, Größen-, Breiten- oder Markertyplegende</span><span class="sxs-lookup"><span data-stu-id="65b32-207">To change the contents of a color, size, width, or marker type legend</span></span>  
  
1.  <span data-ttu-id="65b32-208">Klicken Sie in der Entwurfsansicht auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="65b32-208">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="65b32-209">Klicken Sie mit der rechten Maustaste auf die Ebene mit den gewünschten Daten, und klicken Sie dann auf _\<map element type\>_ **Regel**.</span><span class="sxs-lookup"><span data-stu-id="65b32-209">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Rule**.</span></span>  
  
3.  <span data-ttu-id="65b32-210">Überprüfen **Sie, ob Daten mithilfe von** anzeigen \<*rule type*> ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="65b32-210">Verify that **Visualize data by using** \<*rule type*> is selected.</span></span>  
  
4.  <span data-ttu-id="65b32-211">Überprüfen Sie in **Datenfeld**, ob die analytischen Daten, die Sie auf der Ebene visuell darstellen, ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="65b32-211">In **Data field**, verify that the analytical data that you are visualizing on the layer is selected.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="65b32-212">Wenn keine Felder in der Dropdownliste angezeigt werden, klicken mit der rechten Maustaste auf die Ebene, und klicken Sie anschließend auf **Ebenendaten** , um die Seite „Analytische Daten“ im Dialogfeld „Kartenebenendaten-Eigenschaften“, zu öffnen. Überprüfen Sie auch, ob Sie analytische Daten für diese Ebene angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="65b32-212">If no fields appear in the drop-down list, right-click the layer, and then click **Layer Data** to open the Map Layer Data Properties Dialog Box, Analytical Data page and verify that you have specified analytical data for this layer.</span></span>  
  
5.  <span data-ttu-id="65b32-213">Klicken Sie auf **Legende**.</span><span class="sxs-lookup"><span data-stu-id="65b32-213">Click **Legend**.</span></span>  
  
6.  <span data-ttu-id="65b32-214">Wählen Sie unter **In dieser Legende anzeigen**die Kartenlegende für die Anzeige der Regelergebnisse aus.</span><span class="sxs-lookup"><span data-stu-id="65b32-214">In **Show in this legend**, select the map legend to use to display the rule results.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-change-the-contents-of-the-color-scale"></a><a name="ColorScale"></a> <span data-ttu-id="65b32-215">So ändern Sie den Inhalt der Farbskala</span><span class="sxs-lookup"><span data-stu-id="65b32-215">To change the contents of the color scale</span></span>  
  
#### <a name="to-change-the-contents-of-the-color-scale-or-a-color-legend"></a><span data-ttu-id="65b32-216">So ändern Sie den Inhalt der Farbskala oder einer Farblegende</span><span class="sxs-lookup"><span data-stu-id="65b32-216">To change the contents of the color scale or a color legend</span></span>  
  
1.  <span data-ttu-id="65b32-217">Klicken Sie in der Entwurfsansicht auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="65b32-217">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="65b32-218">Klicken Sie mit der rechten Maustaste auf die Ebene mit den gewünschten Daten, und klicken Sie dann auf _\<map element type\>_ **Farbregel**.</span><span class="sxs-lookup"><span data-stu-id="65b32-218">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Color Rule**.</span></span>  
  
3.  <span data-ttu-id="65b32-219">Aktivieren Sie die zu verwendende Farbregeloption.</span><span class="sxs-lookup"><span data-stu-id="65b32-219">Select the color rule option to use.</span></span> <span data-ttu-id="65b32-220">Um Elemente in einer Karten Legende oder Farbskala anzuzeigen, müssen Sie eine der Optionen **Daten mithilfe der Option Daten visualisieren** auswählen \<rule type> .</span><span class="sxs-lookup"><span data-stu-id="65b32-220">To display items in a map legend or color scale, you must select one of the **Visualize data by using** \<rule type> options.</span></span>  
  
4.  <span data-ttu-id="65b32-221">Überprüfen Sie in **Datenfeld**, ob die analytischen Daten, die Sie auf der Ebene visuell darstellen, ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="65b32-221">In **Data field**, verify that the analytical data that you are visualizing on the layer is selected.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="65b32-222">Wenn keine Felder in der Dropdownliste angezeigt werden, klicken mit der rechten Maustaste auf die Ebene, und klicken Sie anschließend auf **Ebenendaten** , um die Seite „Analytische Daten“ im Dialogfeld „Kartenebenendaten-Eigenschaften“, zu öffnen. Überprüfen Sie auch, ob Sie analytische Daten für diese Ebene angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="65b32-222">If no fields appear in the drop-down list, right-click the layer, and then click **Layer Data** to open the Map Layer Data Properties Dialog Box, Analytical Data page and verify that you have specified analytical data for this layer.</span></span>  
  
5.  <span data-ttu-id="65b32-223">Klicken Sie auf **Legende**.</span><span class="sxs-lookup"><span data-stu-id="65b32-223">Click **Legend**.</span></span>  
  
6.  <span data-ttu-id="65b32-224">Wählen Sie unter **Farbskalaoptionen**die Option **In Farbskala anzeigen** aus, um die Regelergebnisse in der Farbskala anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="65b32-224">In **Color scale options**, select **Show in color scale** to display the rule results in the color scale.</span></span> <span data-ttu-id="65b32-225">Sie können diese Option für mehrere Farbregeln angeben.</span><span class="sxs-lookup"><span data-stu-id="65b32-225">You can specify this option for more than one color rule.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-remove-all-items-from-a-legend"></a><a name="HideItems"></a> <span data-ttu-id="65b32-226">So entfernen Sie alle Elemente aus einer Legende</span><span class="sxs-lookup"><span data-stu-id="65b32-226">To remove all items from a legend</span></span>  
  
#### <a name="to-hide-items-based-on-a-rule"></a><span data-ttu-id="65b32-227">So blenden Sie Elemente basierend auf einer Regel aus</span><span class="sxs-lookup"><span data-stu-id="65b32-227">To hide items based on a rule</span></span>  
  
1.  <span data-ttu-id="65b32-228">Klicken Sie in der Entwurfsansicht auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="65b32-228">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="65b32-229">Klicken Sie mit der rechten Maustaste auf die Ebene mit den gewünschten Daten, und klicken Sie dann auf _\<map element type\>_ **Regel**.</span><span class="sxs-lookup"><span data-stu-id="65b32-229">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Rule**.</span></span>  
  
3.  <span data-ttu-id="65b32-230">Klicken Sie auf **Legende**.</span><span class="sxs-lookup"><span data-stu-id="65b32-230">Click **Legend**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
##  <a name="to-change-the-format-of-content-in-a-legend"></a><a name="ChangeFormatItems"></a> <span data-ttu-id="65b32-231">So ändern Sie das Format des Inhalts einer Legende</span><span class="sxs-lookup"><span data-stu-id="65b32-231">To change the format of content in a legend</span></span>  
 <span data-ttu-id="65b32-232">Legen Sie Legendenoptionen für die zugeordnete Regel der Kartenlegende fest.</span><span class="sxs-lookup"><span data-stu-id="65b32-232">Set legend options for the rule that is associated with the map legend.</span></span>  
  
#### <a name="to-change-the-format-of-content-in-a-legend"></a><span data-ttu-id="65b32-233">So ändern Sie das Format des Inhalts einer Legende</span><span class="sxs-lookup"><span data-stu-id="65b32-233">To change the format of content in a legend</span></span>  
  
1.  <span data-ttu-id="65b32-234">Klicken Sie in der Entwurfsansicht auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="65b32-234">In Design view, click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="65b32-235">Klicken Sie mit der rechten Maustaste auf die Ebene mit den gewünschten Daten, und klicken Sie dann auf _\<map element type\>_ **Regel**.</span><span class="sxs-lookup"><span data-stu-id="65b32-235">Right-click the layer that has the data that you want, and then click _\<map element type\>_**Rule**.</span></span>  
  
3.  <span data-ttu-id="65b32-236">Klicken Sie auf **Legende**.</span><span class="sxs-lookup"><span data-stu-id="65b32-236">Click **Legend**.</span></span>  
  
4.  <span data-ttu-id="65b32-237">Unter**Legendentext** werden Schlüsselwörter angezeigt, die die in der Legende angezeigten Daten angeben.</span><span class="sxs-lookup"><span data-stu-id="65b32-237">**Legend text** displays keywords that specify which data appears in the legend.</span></span> <span data-ttu-id="65b32-238">Verwenden Sie Kartenschlüsselwörter und benutzerdefinierte Formate, um das Format des Legendentexts zu steuern.</span><span class="sxs-lookup"><span data-stu-id="65b32-238">Use map keywords and custom formats to help control the format of legend text.</span></span> <span data-ttu-id="65b32-239">#FROMVALUE {C2} gibt z. B. ein Währungsformat mit zwei Dezimalstellen an.</span><span class="sxs-lookup"><span data-stu-id="65b32-239">For example, #FROMVALUE {C2} specifies a currency format with two decimal places.</span></span> <span data-ttu-id="65b32-240">Weitere Informationen finden Sie unter [Unterschiedliche Polygon-, Linien- und Punktanzeigen bei der Verwendung von Regeln und analytischen Daten &#40;Berichts-Generator und SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span><span class="sxs-lookup"><span data-stu-id="65b32-240">For more information, see [Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;](vary-polygon-line-and-point-display-by-rules-and-analytical-data.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
  
  
## <a name="see-also"></a><span data-ttu-id="65b32-241">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="65b32-241">See Also</span></span>  
 <span data-ttu-id="65b32-242">[Karten &#40;Berichts-Generator und SSRS&#41;](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="65b32-242">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="65b32-243">[Hinzufügen, Ändern oder Löschen einer Karte oder einer Kartenebene (Berichts-Generator und SSRS)](add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="65b32-243">[Add, Change, or Delete a Map or Map Layer &#40;Report Builder and SSRS&#41;](add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="65b32-244">[Anpassen der Daten und der Anzeige einer Karte oder einer Kartenebene &#40;Berichts-Generator und SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="65b32-244">[Customize the Data and Display of a Map or Map Layer &#40;Report Builder and SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="65b32-245">[Problembehandlung bei Berichten: Kartenberichte &#40;Berichts-Generator und SSRS&#41;](troubleshoot-reports-map-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="65b32-245">[Troubleshoot Reports: Map Reports &#40;Report Builder and SSRS&#41;](troubleshoot-reports-map-reports-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="65b32-246">Karten-Assistent und Kartenebenen-Assistent &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="65b32-246">Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;</span></span>](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md)  
  
  
