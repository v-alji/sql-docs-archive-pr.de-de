---
title: Hinzufügen, Ändern oder Löschen einer Karte oder einer Kartenebene (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10526"
- sql12.rtp.rptdesigner.maptilelayerproperties.general.f1
- "10529"
- "10525"
- "10535"
- sql12.rtp.rptdesigner.mappolygonlayerproperties.general.f1
- sql12.rtp.rptdesigner.shared.layervisibility.f1
- sql12.rtp.rptdesigner.mappointlayerproperties.general.f1
- sql12.rtp.rptdesigner.shared.layerfilters.f1
- "10524"
- sql12.rtp.rptdesigner.maplayerproperties.general.f1
- sql12.rtp.rptdesigner.maplinelayerproperties.general.f1
- "10532"
- "10528"
- "10527"
- sql12.rtp.rptdesigner.maplayerproperties.analyticaldata.f1
ms.assetid: 6e89815e-187e-45bf-bf63-3d5c4a246360
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4e9fd178d36ee3322c0bd94dd44d621439139b71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617766"
---
# <a name="add-change-or-delete-a-map-or-map-layer-report-builder-and-ssrs"></a><span data-ttu-id="0a637-102">Hinzufügen, Ändern oder Löschen einer Karte oder einer Kartenebene (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="0a637-102">Add, Change, or Delete a Map or Map Layer (Report Builder and SSRS)</span></span>
  <span data-ttu-id="0a637-103">Eine Karte ist eine Sammlung von Ebenen.</span><span class="sxs-lookup"><span data-stu-id="0a637-103">A map is a collection of layers.</span></span> <span data-ttu-id="0a637-104">Wenn Sie einem Bericht eine Karte hinzufügen, definieren Sie die erste Ebene.</span><span class="sxs-lookup"><span data-stu-id="0a637-104">When you add a map to a report, you define the first layer.</span></span> <span data-ttu-id="0a637-105">Sie können zusätzliche Ebenen mit dem Kartenebenen-Assistenten erstellen.</span><span class="sxs-lookup"><span data-stu-id="0a637-105">You can create additional layers by using the map layer wizard.</span></span>  
  
 <span data-ttu-id="0a637-106">Optionen können am einfachsten mit dem Kartenebenen-Assistenten hinzugefügt, entfernt oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0a637-106">The easiest way to add, remove, or change options for a layer is to use the map layer wizard.</span></span> <span data-ttu-id="0a637-107">Sie können Optionen über den Bereich Karte auch manuell ändern.</span><span class="sxs-lookup"><span data-stu-id="0a637-107">You can also change options manually from the Map pane.</span></span> <span data-ttu-id="0a637-108">Klicken Sie zum Anzeigen des Bereichs **Karte** in der Karte auf die Entwurfsoberfläche für Berichte.</span><span class="sxs-lookup"><span data-stu-id="0a637-108">To display the **Map** pane, click in the map on the report design surface.</span></span> <span data-ttu-id="0a637-109">Die folgende Abbildung zeigt die Teile des Bereichs an:</span><span class="sxs-lookup"><span data-stu-id="0a637-109">The following figure displays the parts of the pane:</span></span>  
  
 <span data-ttu-id="0a637-110">![rsMapLayerZone](../media/rsmaplayerzone.gif "rsMapLayerZone")</span><span class="sxs-lookup"><span data-stu-id="0a637-110">![rsMapLayerZone](../media/rsmaplayerzone.gif "rsMapLayerZone")</span></span>  
  
 <span data-ttu-id="0a637-111">Kartenebenen werden von unten nach oben in der Reihenfolge gezeichnet, in der sie im Kartenbereich angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="0a637-111">Map layers are drawn from bottom to top in the order that they appear in the Map pane.</span></span> <span data-ttu-id="0a637-112">In der vorstehenden Abbildung wird die Kachelebene zuerst gezeichnet, und die Polygonebene wird zuletzt gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="0a637-112">In the previous figure, the tile layer is drawn first and the polygon layer is drawn last.</span></span> <span data-ttu-id="0a637-113">Ebenen, die später gezeichnet werden, können Kartenelemente auf früher gezeichneten Ebenen verdecken.</span><span class="sxs-lookup"><span data-stu-id="0a637-113">Layers that are drawn later might hide map elements on layers that are drawn earlier.</span></span> <span data-ttu-id="0a637-114">Sie können die Reihenfolge der Ebenen mit den Pfeiltasten auf der Symbolleiste des Bereichs Karte ändern.</span><span class="sxs-lookup"><span data-stu-id="0a637-114">You can change the order of layers by using the arrow keys on the Map pane toolbar.</span></span> <span data-ttu-id="0a637-115">Um Ebenen anzuzeigen oder auszublenden, schalten Sie das Sichtbarkeitssymbol um.</span><span class="sxs-lookup"><span data-stu-id="0a637-115">To show or hide layers, toggle the visibility icon.</span></span> <span data-ttu-id="0a637-116">Sie können die Transparenz einer Ebene auf der `Visibility` Seite des Dialog Felds Eigenschaften für **Ebenendaten** ändern.</span><span class="sxs-lookup"><span data-stu-id="0a637-116">You can change the transparency of a layer on the `Visibility` page of the **Layer Data** properties dialog box.</span></span>  
  
 <span data-ttu-id="0a637-117">In der folgenden Tabelle werden die Symbole für den Bereich **Karte** angezeigt:</span><span class="sxs-lookup"><span data-stu-id="0a637-117">The following table displays the toolbar icons for the **Map** pane.</span></span>  
  
|<span data-ttu-id="0a637-118">Symbol</span><span class="sxs-lookup"><span data-stu-id="0a637-118">Symbol</span></span>|<span data-ttu-id="0a637-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0a637-119">Description</span></span>|<span data-ttu-id="0a637-120">Verwendung</span><span class="sxs-lookup"><span data-stu-id="0a637-120">When to use</span></span>|  
|------------|-----------------|-----------------|  
|<span data-ttu-id="0a637-121">![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")</span><span class="sxs-lookup"><span data-stu-id="0a637-121">![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")</span></span>|<span data-ttu-id="0a637-122">Kartenebenen-Assistent</span><span class="sxs-lookup"><span data-stu-id="0a637-122">Map Layer Wizard</span></span>|<span data-ttu-id="0a637-123">Um mit einem Assistenten eine Ebene hinzuzufügen, klicken Sie auf **Assistent für neue Ebenen**.</span><span class="sxs-lookup"><span data-stu-id="0a637-123">To add a layer by using a wizard, click **New layer wizard**.</span></span>|  
|<span data-ttu-id="0a637-124">![rs_IconMapAddLayer](../../tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer")</span><span class="sxs-lookup"><span data-stu-id="0a637-124">![rs_IconMapAddLayer](../../tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer")</span></span>|<span data-ttu-id="0a637-125">Ebene hinzufügen</span><span class="sxs-lookup"><span data-stu-id="0a637-125">Add Layer</span></span>|<span data-ttu-id="0a637-126">Um manuell eine Ebene hinzuzufügen, klicken Sie auf **Ebene hinzufügen**, und klicken Sie dann auf den Typ der Kartenebene, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="0a637-126">To manually add a layer, click **Add Layer**, and then click the type of map layer to add.</span></span>|  
|<span data-ttu-id="0a637-127">![rs_IconMapPolygonLayer](../media/rs-iconmappolygonlayer.gif "rs_IconMapPolygonLayer")</span><span class="sxs-lookup"><span data-stu-id="0a637-127">![rs_IconMapPolygonLayer](../media/rs-iconmappolygonlayer.gif "rs_IconMapPolygonLayer")</span></span>|<span data-ttu-id="0a637-128">Polygonebene</span><span class="sxs-lookup"><span data-stu-id="0a637-128">Polygon Layer</span></span>|<span data-ttu-id="0a637-129">Fügen Sie eine Kartenebene hinzu, die Bereiche oder Formen anzeigt, die auf Sätzen von Polygonkoordinaten basieren.</span><span class="sxs-lookup"><span data-stu-id="0a637-129">Add a map layer that displays areas or shapes that are based sets of polygon coordinates.</span></span>|  
|<span data-ttu-id="0a637-130">![rs_IconMapLineLayer](../media/rs-iconmaplinelayer.gif "rs_IconMapLineLayer")</span><span class="sxs-lookup"><span data-stu-id="0a637-130">![rs_IconMapLineLayer](../media/rs-iconmaplinelayer.gif "rs_IconMapLineLayer")</span></span>|<span data-ttu-id="0a637-131">Linienebene</span><span class="sxs-lookup"><span data-stu-id="0a637-131">Line Layer</span></span>|<span data-ttu-id="0a637-132">Fügen Sie eine Kartenebene hinzu, die Pfade oder Routen anzeigt, die auf Sätzen von Linienkoordinaten basieren.</span><span class="sxs-lookup"><span data-stu-id="0a637-132">Add a map layer that displays paths or routes that are based on sets of line coordinates.</span></span>|  
|<span data-ttu-id="0a637-133">![rs_IconMapPointLayer](../media/rs-iconmappointlayer.gif "rs_IconMapPointLayer")</span><span class="sxs-lookup"><span data-stu-id="0a637-133">![rs_IconMapPointLayer](../media/rs-iconmappointlayer.gif "rs_IconMapPointLayer")</span></span>|<span data-ttu-id="0a637-134">Punktebene</span><span class="sxs-lookup"><span data-stu-id="0a637-134">Point Layer</span></span>|<span data-ttu-id="0a637-135">Fügen Sie eine Kartenebene hinzu, die Orte anzeigt, die auf Sätzen von Punktkoordinaten basieren.</span><span class="sxs-lookup"><span data-stu-id="0a637-135">Add a map layer that displays locations that are based on sets of point coordinates.</span></span>|  
|<span data-ttu-id="0a637-136">![rs_IconMapTileLayer](../media/rs-iconmaptilelayer.gif "rs_IconMapTileLayer")</span><span class="sxs-lookup"><span data-stu-id="0a637-136">![rs_IconMapTileLayer](../media/rs-iconmaptilelayer.gif "rs_IconMapTileLayer")</span></span>|<span data-ttu-id="0a637-137">Kachelebene</span><span class="sxs-lookup"><span data-stu-id="0a637-137">Tile Layer</span></span>|<span data-ttu-id="0a637-138">Fügen Sie eine Kartenebene hinzu, die Bing Map-Kacheln anzeigt, die dem aktuellen vom Viewport definierten Kartenansichtbereich entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0a637-138">Add a map layer that displays Bing Map tiles that correspond to the current map view area that is defined by the viewport.</span></span>|  
  
 <span data-ttu-id="0a637-139">Am unteren Rand der Karte befindet sich der Kartenansichtsbereich.</span><span class="sxs-lookup"><span data-stu-id="0a637-139">At the bottom of the Map pane is the Map view area.</span></span> <span data-ttu-id="0a637-140">Um die Optionen für Zentrieren und Zoomen der Karte zu ändern, verwenden Sie die Pfeiltasten, um den Ansichtsmittelpunkt festzulegen, und den Schieberegler, um die Zoomstufe festzulegen.</span><span class="sxs-lookup"><span data-stu-id="0a637-140">To change the center or zoom options for the map, use the arrow keys to adjust the view center and the slider to adjust the zoom level.</span></span>  
  
 <span data-ttu-id="0a637-141">Weitere Informationen zu Ebenen finden Sie unter [Karten &#40;Berichts-Generator und SSRS&#41;](maps-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0a637-141">For more information about layers, see [Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="to-add-a-layer-from-the-map-layer-wizard"></a><a name="AddLayer"></a> <span data-ttu-id="0a637-142">So fügen Sie eine Ebene über den Kartenebenen-Assistenten hinzu</span><span class="sxs-lookup"><span data-stu-id="0a637-142">To add a layer from the map layer wizard</span></span>  
  
-   <span data-ttu-id="0a637-143">Klicken Sie auf dem Menüband im Menü **Einfügen** auf **Karte**und dann auf **Karte Wizard.**</span><span class="sxs-lookup"><span data-stu-id="0a637-143">From the Ribbon, on the **Insert** menu, click **Map**, and then click **Map Wizard.**</span></span> <span data-ttu-id="0a637-144">. Mit dem Assistenten können Sie der vorhandenen Karte eine Ebene hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0a637-144">The wizard enables you to add a layer to the existing map.</span></span> <span data-ttu-id="0a637-145">Die meisten Assistentenseiten sind im Karten-Assistenten und im Kartenebenen-Assistenten identisch.</span><span class="sxs-lookup"><span data-stu-id="0a637-145">Most wizard pages are identical between the map wizard and the map layer wizard.</span></span>  
  
     <span data-ttu-id="0a637-146">Weitere Informationen finden Sie unter [Karten-Assistent und Kartenebenen-Assistent &#40;Berichts-Generator und SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0a637-146">For more information, see [Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span></span>  

##  <a name="to-change-options-for-a-layer-by-using-the-map-layer-wizard"></a><a name="ChangeLayer"></a> <span data-ttu-id="0a637-147">So ändern Sie die Optionen für eine Ebene mit dem Kartenebenen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="0a637-147">To change options for a layer by using the map layer wizard</span></span>  
  
-   <span data-ttu-id="0a637-148">Führen Sie den Karten-Assistenten aus.</span><span class="sxs-lookup"><span data-stu-id="0a637-148">Run the map layer wizard.</span></span> <span data-ttu-id="0a637-149">Mit diesem Assistenten können Sie die Optionen für eine von Ihnen erstellte Ebene mithilfe des Kartenebenen-Assistenten ändern.</span><span class="sxs-lookup"><span data-stu-id="0a637-149">This wizard enables you to change options for a layer that you created by using the map layer wizard.</span></span> <span data-ttu-id="0a637-150">Klicken Sie zuerst im Kartenbereich mit der rechten Maustaste auf die Ebene, und dann in der Symbolleiste auf die Schaltfläche für den Ebenen-Assistenten (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span><span class="sxs-lookup"><span data-stu-id="0a637-150">In the Map pane, right-click the layer, and on the toolbar, click the layer wizard button (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span></span>  
  
     <span data-ttu-id="0a637-151">Weitere Informationen finden Sie unter [Karten-Assistent und Kartenebenen-Assistent &#40;Berichts-Generator und SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0a637-151">For more information, see [Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;](map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md).</span></span>  

##  <a name="to-add-a-point-line-or-polygon-layer-from-the-map-pane-toolbar"></a><a name="AddVectorLayer"></a> <span data-ttu-id="0a637-152">So fügen Sie eine Punkt-, Linien- oder Polygonebene über die Symbolleiste des Kartenbereichs hinzu</span><span class="sxs-lookup"><span data-stu-id="0a637-152">To add a point, line, or polygon layer from the Map pane toolbar</span></span>  
  
1.  <span data-ttu-id="0a637-153">Klicken Sie auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0a637-153">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0a637-154">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ebene hinzufügen**, und klicken Sie in der Dropdownliste auf den Typ der Ebene, die Sie hinzufügen möchten: **Punkt**, **Linie**oder **Polygon**.</span><span class="sxs-lookup"><span data-stu-id="0a637-154">On the toolbar, click the **Add Layer** button, and from the drop-down list, click the type of layer that you want to add: **Point**, **Line**, or **Polygon**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0a637-155">Sie können eine Kartenebene auch manuell hinzufügen und konfigurieren. Es empfiehlt sich jedoch, neue Ebenen mit dem Kartenebenen-Assistenten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0a637-155">Although you can add a map layer and configure it manually, we recommend that you use the map layer wizard to add new layers.</span></span> <span data-ttu-id="0a637-156">Wenn Sie den Assistenten über die Symbolleiste des Kartenbereichs starten möchten, klicken Sie auf die Schaltfläche für den Ebenen-Assistenten (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span><span class="sxs-lookup"><span data-stu-id="0a637-156">To launch the wizard from the Map pane toolbar, click the layer wizard button (![rs_IconMapLayerWizard](../../tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard")).</span></span>  
  
3.  <span data-ttu-id="0a637-157">Klicken Sie mit der rechten Maustaste auf die Ebene, und klicken Sie anschließend auf **Ebenendaten**.</span><span class="sxs-lookup"><span data-stu-id="0a637-157">Right-click the layer, and then click **Layer Data**.</span></span>  
  
4.  <span data-ttu-id="0a637-158">Wählen Sie unter **Räumliche Daten verwenden aus**die Quelle räumlicher Daten aus.</span><span class="sxs-lookup"><span data-stu-id="0a637-158">In **Use spatial data from**, select the source of spatial data.</span></span> <span data-ttu-id="0a637-159">Die Optionen hängen von der Auswahl ab.</span><span class="sxs-lookup"><span data-stu-id="0a637-159">Options vary based on your selection.</span></span>  
  
     <span data-ttu-id="0a637-160">Wenn Sie analytische Daten aus dem Bericht auf dieser Ebene darstellen möchten, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="0a637-160">If you want to visualize analytical from your report on this layer, do the following:</span></span>  
  
    1.  <span data-ttu-id="0a637-161">Klicken Sie auf **Analytische Daten**.</span><span class="sxs-lookup"><span data-stu-id="0a637-161">Click **Analytical data**.</span></span>  
  
    2.  <span data-ttu-id="0a637-162">Klicken Sie unter **Analytisches Dataset**auf den Namen des Datasets, das die analytische Daten und die Übereinstimmungsfelder enthält, mit denen eine Beziehung zwischen analytischen und räumlichen Daten hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0a637-162">In **Analytical dataset**, click the name of the dataset that contains analytical data and the match fields to build a relationship between analytical and spatial data.</span></span>  
  
    3.  <span data-ttu-id="0a637-163">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0a637-163">Click **Add**.</span></span>  
  
    4.  <span data-ttu-id="0a637-164">Geben Sie den Namen des Übereinstimmungsfelds aus dem räumlichen Dataset ein.</span><span class="sxs-lookup"><span data-stu-id="0a637-164">Type the name of the match field from the spatial dataset.</span></span>  
  
    5.  <span data-ttu-id="0a637-165">Geben Sie den Namen des Übereinstimmungsfelds aus dem analytischen Dataset ein.</span><span class="sxs-lookup"><span data-stu-id="0a637-165">Type the name of the match field from the analytical dataset.</span></span>  
  
     <span data-ttu-id="0a637-166">Weitere Informationen zum Verknüpfen räumlicher und analytischer Daten finden Sie unter [Anpassen der Daten und der Anzeige einer Karte oder einer Kartenebene &#40;Berichts-Generator und SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0a637-166">For more information about linking spatial and analytical data, see [Customize the Data and Display of a Map or Map Layer &#40;Report Builder and SSRS&#41;](customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-filter-analytical-data-for-the-layer"></a><a name="FilterAnalyticalData"></a> <span data-ttu-id="0a637-167">So filtern Sie analytische Daten für die Ebene</span><span class="sxs-lookup"><span data-stu-id="0a637-167">To filter analytical data for the layer</span></span>  
  
1.  <span data-ttu-id="0a637-168">Klicken Sie auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0a637-168">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0a637-169">Klicken Sie mit der rechten Maustaste in den Kartenbereich, und klicken Sie anschließend auf  **Ebenendaten**.</span><span class="sxs-lookup"><span data-stu-id="0a637-169">Right-click the layer in the Map pane, and then click  **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="0a637-170">Klicken Sie auf **Filter**.</span><span class="sxs-lookup"><span data-stu-id="0a637-170">Click **Filters**.</span></span>  
  
4.  <span data-ttu-id="0a637-171">Definieren Sie eine Filtergleichung, um die in der Kartenanzeige verwendeten analytischen Daten zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="0a637-171">Define a filter equation to limit the analytical data that is used in the map display.</span></span> <span data-ttu-id="0a637-172">Weitere Informationen finden Sie unter [Beispiele für Filtergleichungen &#40;Berichts-Generator und SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0a637-172">For more information, see [Filter Equation Examples &#40;Report Builder and SSRS&#41;](filter-equation-examples-report-builder-and-ssrs.md).</span></span>  

##  <a name="to-control-point-properties-for-a-point-layer-or-for-polygon-center-points"></a><a name="PointProperties"></a> <span data-ttu-id="0a637-173">So steuern Sie Punkteigenschaften für eine Punktebene oder für Polygonmittelpunkte</span><span class="sxs-lookup"><span data-stu-id="0a637-173">To control point properties for a point layer or for polygon center points</span></span>  
  
1.  <span data-ttu-id="0a637-174">Wählen Sie **Allgemein** im Dialogfeld **Punkteigenschaften von Karten** aus, um Bezeichnung, QuickInfo und Markertypoptionen für die folgenden Kartenelemente zu ändern:</span><span class="sxs-lookup"><span data-stu-id="0a637-174">Select **General** on the **Map Point Properties** dialog box to change label, tooltip, and marker type options for the following map elements:</span></span>  
  
    -   <span data-ttu-id="0a637-175">Alle dynamischen oder eingebettete Punkte auf einer Punktebene.</span><span class="sxs-lookup"><span data-stu-id="0a637-175">All dynamic or embedded points on a point layer.</span></span> <span data-ttu-id="0a637-176">Farbregeln, Größenregeln und Markertypregeln für Punkte überschreiben diese Optionen.</span><span class="sxs-lookup"><span data-stu-id="0a637-176">Color rules, size rules, and marker type rules for points override these options.</span></span> <span data-ttu-id="0a637-177">Um Optionen für einen bestimmten eingebetteten Punkt zu überschreiben, verwenden Sie die Seite [Map Embedded Point Properties Dialog Box, Marker](../map-embedded-point-properties-dialog-box-marker.md) .</span><span class="sxs-lookup"><span data-stu-id="0a637-177">To override options for a specific embedded point, use the [Map Embedded Point Properties Dialog Box, Marker](../map-embedded-point-properties-dialog-box-marker.md) page.</span></span>  
  
    -   <span data-ttu-id="0a637-178">Der Mittelpunkt für alle dynamischen oder eingebetteten Polygone auf einer Polygonebene.</span><span class="sxs-lookup"><span data-stu-id="0a637-178">The center point for all dynamic or embedded polygons on a polygon layer.</span></span> <span data-ttu-id="0a637-179">Farbregeln, Größenregeln und Markertypregeln für Mittelpunkte überschreiben diese Optionen.</span><span class="sxs-lookup"><span data-stu-id="0a637-179">Color rules, size rules, and marker type rules for center points override these options.</span></span> <span data-ttu-id="0a637-180">Verwenden Sie die Seite [Eigenschaften für eingebettete Punkte der Karte (Dialogfeld), Marker](../map-embedded-point-properties-dialog-box-marker.md) , um Optionen für einen bestimmten eingebetteten Punkt zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="0a637-180">To override options for a specific center point, use the [Map Embedded Point Properties Dialog Box, Marker](../map-embedded-point-properties-dialog-box-marker.md) page.</span></span>  

##  <a name="to-specify-embedded-data-as-a-source-of-spatial-data"></a><a name="Embedded"></a> <span data-ttu-id="0a637-181">So geben Sie eingebettete Daten als Quelle räumlicher Daten an</span><span class="sxs-lookup"><span data-stu-id="0a637-181">To specify embedded data as a source of spatial data</span></span>  
  
1.  <span data-ttu-id="0a637-182">Klicken Sie auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0a637-182">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0a637-183">Klicken Sie mit der rechten Maustaste auf die Ebene, und klicken Sie anschließend auf **Ebenendaten**.</span><span class="sxs-lookup"><span data-stu-id="0a637-183">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="0a637-184">Wählen Sie unter **Räumliche Daten verwenden aus**den Wert **In Bericht eingebettete Daten**aus.</span><span class="sxs-lookup"><span data-stu-id="0a637-184">In **Use spatial data from**, select **Data embedded in report**.</span></span>  
  
4.  <span data-ttu-id="0a637-185">Um Kartenelemente aus einem vorhandenen Bericht zu laden oder Kartenelemente auf der Grundlage einer ESRI-Datei zu erstellen, klicken Sie auf **Durchsuchen**, zeigen Sie auf die Datei, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="0a637-185">To load map elements from an existing report or to create map elements based on an ESRI file, click **Browse**, point to the file, and then click **Open**.</span></span> <span data-ttu-id="0a637-186">Die Kartenelemente werden in diese Berichtsdefinition eingebettet.</span><span class="sxs-lookup"><span data-stu-id="0a637-186">The map elements are embedded in this report definition.</span></span> <span data-ttu-id="0a637-187">Die räumlichen Daten, auf die Sie zeigen, müssen zum Ebenentyp passen.</span><span class="sxs-lookup"><span data-stu-id="0a637-187">The spatial data that you point to must match the layer type.</span></span> <span data-ttu-id="0a637-188">Beispielsweise müssen Sie für eine Punktebene auf räumliche Daten zeigen, die Sätze von Punktkoordinaten angeben.</span><span class="sxs-lookup"><span data-stu-id="0a637-188">For example, for a point layer, you must point to spatial data that specifies sets of point coordinates.</span></span>  
  
5.  <span data-ttu-id="0a637-189">Geben Sie unter **Räumliches Feld**den Namen des Felds an, das räumliche Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="0a637-189">In **Spatial field**, specify the name of the field that contains spatial data.</span></span> <span data-ttu-id="0a637-190">Möglicherweise müssen Sie diesen Namen anhand der Quelle räumlicher Daten bestimmen.</span><span class="sxs-lookup"><span data-stu-id="0a637-190">You might need to determine this name from the source of spatial data.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0a637-191">Wenn Sie den Namen des Felds nicht kennen und zu einer ESRI-Shape-Datei gewechselt haben, verwenden Sie statt dieser Option die Option **Mit ESRI-Shape-Datei verknüpfen** .</span><span class="sxs-lookup"><span data-stu-id="0a637-191">If you do not know the name of the field and you browsed to an ESRI Shapefile, use the **Link to ESRI shape file option** instead of this option.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-specify-an-esri-shapefile-as-a-source-of-spatial-data"></a><a name="ESRI"></a> <span data-ttu-id="0a637-192">So geben Sie eine ESRI-Shape-Datei als Quelle räumlicher Daten an</span><span class="sxs-lookup"><span data-stu-id="0a637-192">To specify an ESRI Shapefile as a source of spatial data</span></span>  
  
1.  <span data-ttu-id="0a637-193">Klicken Sie auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0a637-193">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0a637-194">Klicken Sie mit der rechten Maustaste auf die Ebene, und klicken Sie anschließend auf **Ebenendaten**.</span><span class="sxs-lookup"><span data-stu-id="0a637-194">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="0a637-195">Wählen Sie unter **Räumliche Daten verwenden aus**den Eintrag **Mit ESRI-Shape-Datei verknüpfen**aus.</span><span class="sxs-lookup"><span data-stu-id="0a637-195">In **Use spatial data from**, select **Link to ESRI Shapefile**.</span></span>  
  
4.  <span data-ttu-id="0a637-196">Geben Sie unter **Dateiname**den Speicherort einer ESRI-Shape-Datei ein, oder klicken Sie auf **Durchsuchen** , um eine ESRI-Shape-Datei auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="0a637-196">In **File name**, type the location of an ESRI Shapefile, or click **Browse** to select an ESRI Shapefile.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0a637-197">Wenn sich die Shape-Datei auf dem lokalen Computer befindet, werden die räumlichen Daten in die Berichtsdefinition eingebettet.</span><span class="sxs-lookup"><span data-stu-id="0a637-197">If the Shapefile is on your local computer, the spatial data is embedded in the report definition.</span></span> <span data-ttu-id="0a637-198">Um die Daten bei der Verarbeitung des Berichts dynamisch abzurufen, müssen Sie die ESRI-Shape-Datei (.shp) und die zugehörige Unterstützungsdatei (.dbf) auf den Berichtsserver hochladen.</span><span class="sxs-lookup"><span data-stu-id="0a637-198">To retrieve the data dynamically when the report is processed, you must upload the ESRI .shp file and its .dbf support file to the report server.</span></span> <span data-ttu-id="0a637-199">Weitere Informationen finden Sie unter „Vorgehensweise: Hochladen einer Datei oder eines Berichts (Berichts-Manager)“ in der [Reporting Services-Dokumentation](https://go.microsoft.com/fwlink/?linkid=121312) in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="0a637-199">For more information, see " How to: Upload a File or Report (Report Manager)" in the [Reporting Services documentation](https://go.microsoft.com/fwlink/?linkid=121312) in SQL Server Books Online.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-specify-a-report-dataset-field-as-a-source-of-spatial-data"></a><a name="DatasetField"></a> <span data-ttu-id="0a637-200">So geben Sie ein Berichtsdataset-Feld als Quelle räumlicher Daten an</span><span class="sxs-lookup"><span data-stu-id="0a637-200">To specify a report dataset field as a source of spatial data</span></span>  
  
1.  <span data-ttu-id="0a637-201">Klicken Sie auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0a637-201">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0a637-202">Klicken Sie mit der rechten Maustaste auf die Ebene, und klicken Sie anschließend auf **Ebenendaten**.</span><span class="sxs-lookup"><span data-stu-id="0a637-202">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="0a637-203">Wählen Sie unter **Räumliche Daten verwenden aus**den Eintrag **Räumliches Feld in einem Dataset**aus.</span><span class="sxs-lookup"><span data-stu-id="0a637-203">In **Use spatial data from**, select **Spatial field in a dataset**.</span></span>  
  
4.  <span data-ttu-id="0a637-204">Klicken Sie unter **Datasetname**auf den Namen eines Datasets in dem Bericht, das die gewünschten räumlichen Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="0a637-204">In **Dataset name**, click the name of a dataset in the report that contains that spatial data that you want.</span></span>  
  
5.  <span data-ttu-id="0a637-205">Klicken Sie unter **Name des räumlichen Felds**auf den Namen des Felds im Dataset, das räumliche Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="0a637-205">In **Spatial field name**, click the name of the field in the dataset that contains spatial data.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-add-a-tile-layer"></a><a name="TileLayer"></a> <span data-ttu-id="0a637-206">So fügen Sie eine Kachelebene hinzu</span><span class="sxs-lookup"><span data-stu-id="0a637-206">To add a tile layer</span></span>  
  
1.  <span data-ttu-id="0a637-207">Klicken Sie auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0a637-207">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0a637-208">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ebene hinzufügen** , und klicken Sie in der Dropdownliste auf **Kachelebene**.</span><span class="sxs-lookup"><span data-stu-id="0a637-208">On the toolbar, click the **Add Layer** button, and from the drop-down list, click **Tile Layer**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0a637-209"> Weitere Informationen zur Verwendung von Bing-Kartenkacheln im Bericht finden Sie in den [zusätzlichen Nutzungsbedingungen](https://go.microsoft.com/fwlink/?LinkId=151371) und der [Datenschutzerklärung](https://go.microsoft.com/fwlink/?LinkId=151372).</span><span class="sxs-lookup"><span data-stu-id="0a637-209">For more information about the use of Bing map tiles in your report, see [Additional Terms of Use](https://go.microsoft.com/fwlink/?LinkId=151371) and [Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=151372).</span></span>  
  
3.  <span data-ttu-id="0a637-210">Klicken Sie mit der rechten Maustaste im Kartenbereich auf die Kachelebene, und klicken Sie anschließend auf **Kacheleigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="0a637-210">Right-click the tile layer in the Map pane, and then click **Tile Properties**.</span></span>  
  
4.  <span data-ttu-id="0a637-211">Wählen Sie unter **Anordnungsoptionen**ein Kachelformat aus.</span><span class="sxs-lookup"><span data-stu-id="0a637-211">In **Tile options**, select a tile style.</span></span> <span data-ttu-id="0a637-212">Wenn die Bing-Kartenkacheln verfügbar sind, wird die Ebene auf der Entwurfsoberfläche anhand des ausgewählten Formats aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0a637-212">If the Bing map tiles are available, the layer on the design surface updates with the style that you select.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0a637-213">Eine Kachelebene kann auch hinzugefügt werden, wenn Sie im Karten-Assistenten oder im Kartenebenen-Assistenten eine Polygon-, Linien- oder Punktebene hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0a637-213">A tile layer can also be added when you add a polygon, line, or point layer in the Map or Map Layer wizard.</span></span> <span data-ttu-id="0a637-214">Wählen Sie auf der Seite **Optionen für räumliche Daten und Kartenansicht auswählen** die Option **Bing Maps-Hintergrund für diese Kartenansicht hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="0a637-214">On the **Choose spatial data and map view options** page, select the option **Add a Bing Maps background for this map view**.</span></span>  

##  <a name="to-change-the-drawing-order-of-a-layer"></a><a name="DrawingOrder"></a> <span data-ttu-id="0a637-215">So ändern Sie die Zeichnungsreihenfolge einer Ebene</span><span class="sxs-lookup"><span data-stu-id="0a637-215">To change the drawing order of a layer</span></span>  
  
1.  <span data-ttu-id="0a637-216">Klicken Sie auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0a637-216">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0a637-217">Klicken Sie im Kartenbereich auf die Ebene, um sie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="0a637-217">Click the layer in the Map pane to select it.</span></span>  
  
3.  <span data-ttu-id="0a637-218">Klicken Sie auf der Symbolleiste des Kartenbereichs auf die NACH-OBEN- oder NACH-UNTEN-TASTE, um die Zeichnungsreihenfolge der einzelnen Ebenen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0a637-218">On the Map pane toolbar, click the up or down arrow to change the drawing order of each layer.</span></span>  

##  <a name="to-change-the-transparency-of-a-polygon-line-or-point-layer"></a><a name="Transparency"></a> <span data-ttu-id="0a637-219">So ändern Sie die Transparenz einer Polygon-, Linien- oder Punktebene</span><span class="sxs-lookup"><span data-stu-id="0a637-219">To change the transparency of a polygon, line, or point layer</span></span>  
  
1.  <span data-ttu-id="0a637-220">Klicken Sie auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0a637-220">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0a637-221">Klicken Sie mit der rechten Maustaste auf die Ebene, und klicken Sie anschließend auf **Ebenendaten**.</span><span class="sxs-lookup"><span data-stu-id="0a637-221">Right-click the layer, and then click **Layer Data**.</span></span>  
  
3.  <span data-ttu-id="0a637-222">Klicken Sie auf `Visibility`.</span><span class="sxs-lookup"><span data-stu-id="0a637-222">Click `Visibility`.</span></span>  
  
4.  <span data-ttu-id="0a637-223">Geben Sie unter **Transparenzoptionen**einen Wert ein, der die Transparenz in Prozent darstellt, z. B. **40**.</span><span class="sxs-lookup"><span data-stu-id="0a637-223">In **Transparency options**, type a value that represents the percentage transparency, for example, **40**.</span></span> <span data-ttu-id="0a637-224">0 (null) % Transparenz bedeutet, dass die Ebene nicht transparent ist.</span><span class="sxs-lookup"><span data-stu-id="0a637-224">Zero (0) % transparency means that the layer is opaque.</span></span> <span data-ttu-id="0a637-225">100 % Transparenz bedeutet, dass die Ebene im Bericht nicht sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="0a637-225">100% transparency means that you will not see the layer in the report.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-change-the-transparency-of-a-tile-layer"></a><a name="TileTransparency"></a> <span data-ttu-id="0a637-226">So ändern Sie die Transparenz einer Kachelebene</span><span class="sxs-lookup"><span data-stu-id="0a637-226">To change the transparency of a tile layer</span></span>  
  
1.  <span data-ttu-id="0a637-227">Klicken Sie auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0a637-227">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0a637-228">Klicken Sie mit der rechten Maustaste auf die Ebene, und klicken Sie anschließend auf **Kacheleigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="0a637-228">Right-click the layer, and then click **Tile Properties**.</span></span>  
  
3.  <span data-ttu-id="0a637-229">Klicken Sie auf `Visibility`.</span><span class="sxs-lookup"><span data-stu-id="0a637-229">Click `Visibility`.</span></span>  
  
4.  <span data-ttu-id="0a637-230">Geben Sie unter **Transparenzoptionen**einen Wert ein, der die Transparenz in Prozent darstellt, z. B. **40**.</span><span class="sxs-lookup"><span data-stu-id="0a637-230">In **Transparency options**, type a value that represents the percentage transparency, for example, **40**.</span></span>  
  
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  

##  <a name="to-specify-a-secure-connection-for-a-tile-layer"></a><a name="Secure"></a> <span data-ttu-id="0a637-231">So geben Sie eine sichere Verbindung für eine Kachelebene an</span><span class="sxs-lookup"><span data-stu-id="0a637-231">To specify a secure connection for a tile layer</span></span>  
  
1.  <span data-ttu-id="0a637-232">Klicken Sie auf die Karte, bis der Kartenbereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0a637-232">Click the map until the Map pane appears.</span></span>  
  
2.  <span data-ttu-id="0a637-233">Klicken Sie im Kartenbereich auf die Kachelebene, um sie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="0a637-233">In the Map pane, click the tile layer to select it.</span></span> <span data-ttu-id="0a637-234">Im Eigenschaftenbereich werden die Eigenschaften der Kachelebene angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0a637-234">The Properties pane displays the tile layer properties.</span></span>  
  
3.  <span data-ttu-id="0a637-235">Legen Sie im Bereich „Eigenschaften“ UseSecureConnection auf **TRUE**fest.</span><span class="sxs-lookup"><span data-stu-id="0a637-235">In the Properties pane, set UseSecureConnection to **True**.</span></span>  
  
 <span data-ttu-id="0a637-236">Die Verbindung für den Bing Maps-Webdienst ruft Bing Maps-Kacheln für diese Ebene mithilfe des HTTP-SSL (Secure Sockets Layer)-Diensts ab.</span><span class="sxs-lookup"><span data-stu-id="0a637-236">The connection for the Bing Maps Web service will use the HTTP SSL (Secure Sockets Layer) service to retrieve Bing map tiles for this layer.</span></span>  

##  <a name="to-specify-the-language-for-tile-labels"></a><a name="Language"></a> <span data-ttu-id="0a637-237">So geben Sie die Sprache für Kachelbezeichnungen an</span><span class="sxs-lookup"><span data-stu-id="0a637-237">To specify the language for tile labels</span></span>  
  
1.  <span data-ttu-id="0a637-238">Standardmäßig wird die Sprache für Kachelformate mit Bezeichnungen vom Standardgebietsschema für den Berichts-Generator bestimmt.</span><span class="sxs-lookup"><span data-stu-id="0a637-238">By default, for tile styles that display labels, the language is determined from the default locale for Report Builder.</span></span> <span data-ttu-id="0a637-239">Sie können die Spracheinstellung für Kachelbezeichnungen auf die folgende Weise anpassen.</span><span class="sxs-lookup"><span data-stu-id="0a637-239">You can customize the language setting for tile labels in the following ways.</span></span>  
  
    -   <span data-ttu-id="0a637-240">Klicken Sie auf die Karte außerhalb des Viewports, um die Karte auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="0a637-240">Click the map outside the viewport to select the map.</span></span> <span data-ttu-id="0a637-241">Wählen Sie im Eigenschaftenbereich aus der Dropdownliste einen Kulturwert für die TileLanguage-Eigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="0a637-241">In the Properties pane, for the TileLanguage property, select a culture value from the drop-down list.</span></span>  
  
    -   <span data-ttu-id="0a637-242">Klicken Sie auf den Berichtshintergrund, um den Bericht auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="0a637-242">Click the report background to select the report.</span></span> <span data-ttu-id="0a637-243">Wählen Sie im Eigenschaftenbereich aus der Dropdownliste einen Kulturwert für die Language-Eigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="0a637-243">In the Properties pane, from for the Language property, select a culture value from the drop-down list.</span></span>  
  
     <span data-ttu-id="0a637-244">Die Reihenfolge zum Festlegen der Kachelbezeichnungssprache ist: Berichtseigenschaft „Language“, Standardgebietsschema für den Berichts-Generator und Karteneigenschaft „TileLanguage“.</span><span class="sxs-lookup"><span data-stu-id="0a637-244">The order of precedence for setting the tile label language is: report property Language, default locale for Report Builder, and map property TileLanguage.</span></span>  

##  <a name="to-conditionally-hide-a-layer-based-on-viewport-zoom-level"></a><a name="ConditionalHide"></a> <span data-ttu-id="0a637-245">So blenden Sie eine Ebene auf der Grundlage einer Viewport-Zoomstufe bedingt aus</span><span class="sxs-lookup"><span data-stu-id="0a637-245">To conditionally hide a layer based on viewport zoom level</span></span>  
  
1.  <span data-ttu-id="0a637-246">Legen `Visibility` Sie Optionen fest, um die Anzeige für eine Kartenebene zu steuern.</span><span class="sxs-lookup"><span data-stu-id="0a637-246">Set `Visibility` options to control the display for a map layer.</span></span>  
  
    -   <span data-ttu-id="0a637-247">Klicken Sie im Bereich „Kartenebenen“ mit der rechten Maustaste auf eine Ebene, um sie auszuwählen, und klicken Sie auf der Symbolleiste „Kartenebenen“ auf „Eigenschaften“, um **Kartenebeneneigenschaften**zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0a637-247">In the Map Layers pane, right-click a layer to select it, and on the Map Layers toolbar, click Properties to open **Map Layer Properties**.</span></span>  
  
    -   <span data-ttu-id="0a637-248">Klicken Sie auf `Visibility`.</span><span class="sxs-lookup"><span data-stu-id="0a637-248">Click `Visibility`.</span></span>  
  
    -   <span data-ttu-id="0a637-249">Wählen Sie unter **Ebenensichtbarkeit**die Option Je nach Zoomwert einblenden/ausblenden.</span><span class="sxs-lookup"><span data-stu-id="0a637-249">In Layer visibility, select **Show or hide based on zoom value**.</span></span>  
  
    -   <span data-ttu-id="0a637-250">Geben Sie den minimalen und maximalen Zoomwert für die Anzeige der Ebene ein.</span><span class="sxs-lookup"><span data-stu-id="0a637-250">Enter minimum and maximum zoom values for when display the layer.</span></span>  
  
    -   <span data-ttu-id="0a637-251">Optional.</span><span class="sxs-lookup"><span data-stu-id="0a637-251">Optional.</span></span> <span data-ttu-id="0a637-252">Geben Sie einen Wert für die Transparenz ein.</span><span class="sxs-lookup"><span data-stu-id="0a637-252">Enter a value for transparency.</span></span>  
  
     <span data-ttu-id="0a637-253">Sie können die Ebene auch bedingt ausblenden.</span><span class="sxs-lookup"><span data-stu-id="0a637-253">You can also conditionally hide the layer.</span></span> <span data-ttu-id="0a637-254">Weitere Informationen finden Sie unter [Ausblenden eines Elements &#40;Berichts-Generator und SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="0a637-254">For more information, see [Hide an Item &#40;Report Builder and SSRS&#41;](../report-builder/hide-an-item-report-builder-and-ssrs.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="0a637-255">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a637-255">See Also</span></span>  
 <span data-ttu-id="0a637-256">[Karten &#40;Berichts-Generator und SSRS&#41;](maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="0a637-256">[Maps &#40;Report Builder and SSRS&#41;](maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="0a637-257">Problembehandlung bei Berichten: Kartenberichte &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="0a637-257">Troubleshoot Reports: Map Reports &#40;Report Builder and SSRS&#41;</span></span>](troubleshoot-reports-map-reports-report-builder-and-ssrs.md)  
