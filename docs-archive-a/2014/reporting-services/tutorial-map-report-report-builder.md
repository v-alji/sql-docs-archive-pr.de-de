---
title: 'Tutorial: Kartenbericht (Berichts-Generator) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8d831356-7efa-40cc-ae95-383b3eecf833
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b737bb3fe74eb3524f2944a7458cb4837b1aeedf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722421"
---
# <a name="tutorial-map-report-report-builder"></a><span data-ttu-id="3fc6d-102">Lernprogramm: Kartenbericht (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="3fc6d-102">Tutorial: Map Report (Report Builder)</span></span>
  <span data-ttu-id="3fc6d-103">In diesem Lernprogramm erfahren Sie mehr über die Kartenfunktionen, mit denen Sie Berichtsdaten vor einem geografischen Hintergrund anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-103">This tutorial is designed to help you learn about the map features you can use to display report data against a geographic background.</span></span>  
  
 <span data-ttu-id="3fc6d-104">Karten basieren auf räumlichen Daten, die in der Regel aus Punkten, Linien und Polygonen bestehen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-104">Maps are based on spatial data that typically consists of points, lines, and polygons.</span></span> <span data-ttu-id="3fc6d-105">Ein Polygon kann z. B. den Umriss eines Countys darstellen, eine Linie eine Straße und ein Punkt die Position eines Orts.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-105">For example, a polygon can represent the outline of a county, a line can represent a road, and a point can represent the location of a city.</span></span> <span data-ttu-id="3fc6d-106">Jeder räumliche Datentyp wird auf einer separaten Kartenebene als Satz von Kartenelementen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-106">Each type of spatial data is displayed on a separate map layer as a set of map elements.</span></span>  
  
 <span data-ttu-id="3fc6d-107">Geben Sie zum Verändern der Darstellung von Kartenelementen ein Feld mit Werten an, durch die die Kartenelemente mit analytischen Daten aus einem Dataset verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-107">To vary the appearance of map elements, you specify a field that has values that match the map elements with analytical data from a dataset.</span></span> <span data-ttu-id="3fc6d-108">Sie können auch Regeln definieren, durch die Farbe, Größe oder andere Eigenschaften basierend auf Datenbereichen verändert werden.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-108">You can also define rules that vary color, size, or other properties based on ranges of data.</span></span>  
  
 <span data-ttu-id="3fc6d-109">In diesem Lernprogramm erstellen Sie einen Kartenbericht, in dem Geschäftsstandorte in Countys des Bundesstaats New York angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-109">In this tutorial, you will build a map report that displays store locations in New York state counties.</span></span>  
  
##  <a name="what-you-will-learn"></a><a name="BackToTop"></a><span data-ttu-id="3fc6d-110">Was Sie lernen werden</span><span class="sxs-lookup"><span data-stu-id="3fc6d-110">What You Will Learn</span></span>  
 <span data-ttu-id="3fc6d-111">In diesem Lernprogramm lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3fc6d-111">In this tutorial you will learn how to do the following:</span></span>  
  
1.  [<span data-ttu-id="3fc6d-112">Erstellen einer Karte mit einer Polygonebene im Karten-Assistenten</span><span class="sxs-lookup"><span data-stu-id="3fc6d-112">Create a Map with a Polygon Layer from the Map Wizard</span></span>](#Map)  
  
2.  [<span data-ttu-id="3fc6d-113">Hinzufügen einer Kartenpunktebene, um Geschäftsstandorte anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="3fc6d-113">Add a Map Point Layer to Display Store Locations</span></span>](#PointLayer)  
  
3.  [<span data-ttu-id="3fc6d-114">Hinzufügen einer Kartenlinienebene, um eine Route anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="3fc6d-114">Add a Map Line Layer to Display a Route</span></span>](#LineLayer)  
  
4.  [<span data-ttu-id="3fc6d-115">Hinzufügen eines Bing Maps-Kachelhintergrunds</span><span class="sxs-lookup"><span data-stu-id="3fc6d-115">Add a Bing Maps Tile Background</span></span>](#TileLayer)  
  
5.  [<span data-ttu-id="3fc6d-116">Transparente Darstellung einer Ebene</span><span class="sxs-lookup"><span data-stu-id="3fc6d-116">Make a Layer Transparent</span></span>](#Transparent)  
  
6.  [<span data-ttu-id="3fc6d-117">Verändern der Countyfarbe basierend auf Umsätzen</span><span class="sxs-lookup"><span data-stu-id="3fc6d-117">Vary County Color Based on Sales</span></span>](#Vary)  
  
    1.  [<span data-ttu-id="3fc6d-118">Erstellen einer Beziehung zwischen räumlichen und analytischen Daten</span><span class="sxs-lookup"><span data-stu-id="3fc6d-118">Build a Relationship between Spatial and Analytical Data</span></span>](#Relationship)  
  
    2.  [<span data-ttu-id="3fc6d-119">Festlegen von Farbregeln für Polygone</span><span class="sxs-lookup"><span data-stu-id="3fc6d-119">Specify Color Rules for Polygons</span></span>](#ColorRules)  
  
    3.  [<span data-ttu-id="3fc6d-120">Formatieren der Daten in der Farbskala als Währung</span><span class="sxs-lookup"><span data-stu-id="3fc6d-120">Format the Data in the Color Scale as Currency</span></span>](#ColorScale)  
  
    4.  [<span data-ttu-id="3fc6d-121">Erstellen einer neuen Legende</span><span class="sxs-lookup"><span data-stu-id="3fc6d-121">Create a New Legend</span></span>](#NewLegend)  
  
    5.  [<span data-ttu-id="3fc6d-122">Zuordnen der Legende und Farbregeln</span><span class="sxs-lookup"><span data-stu-id="3fc6d-122">Associate Legend and Color Rules</span></span>](#Associate)  
  
    6.  [<span data-ttu-id="3fc6d-123">Löschen der Farbe aus Countys ohne Daten</span><span class="sxs-lookup"><span data-stu-id="3fc6d-123">Clear Color from Counties with No Data</span></span>](#NoData)  
  
7.  [<span data-ttu-id="3fc6d-124">Hinzufügen eines benutzerdefinierten Punkts</span><span class="sxs-lookup"><span data-stu-id="3fc6d-124">Add a Custom Point</span></span>](#CustomPoint)  
  
8.  [<span data-ttu-id="3fc6d-125">Zentrieren der Kartenansicht</span><span class="sxs-lookup"><span data-stu-id="3fc6d-125">Center the Map View</span></span>](#CenterView)  
  
9. [<span data-ttu-id="3fc6d-126">Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="3fc6d-126">Add a Report Title</span></span>](#Title)  
  
10. [<span data-ttu-id="3fc6d-127">Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="3fc6d-127">Save the Report</span></span>](#Save)  
  
> [!NOTE]  
>  <span data-ttu-id="3fc6d-128">In diesem Lernprogramm werden die Schritte für den Assistenten in zwei Verfahren zusammengefasst: ein Verfahren zum Erstellen des Datasets und ein Verfahren zum Erstellen einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-128">In this tutorial, the steps for the wizard are consolidated into two procedures: one to create the dataset and one to create a table.</span></span> <span data-ttu-id="3fc6d-129">Im ersten Tutorial dieser Reihe erhalten Sie ausführliche Anweisungen zum Navigieren zu einem Berichtsserver, Auswählen einer Datenquelle, Erstellen eines Datasets und Ausführen des Assistenten: [Tutorial: Erstellen eines einfachen Tabellenberichts (Berichts-Generator)](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="3fc6d-129">For step-by-step instructions about how to browse to a report server, choose a data source, create a dataset, and run the wizard, see the first tutorial in this series: [Tutorial: Creating a Basic Table Report &#40;Report Builder&#41;](../reporting-services/tutorial-creating-a-basic-table-report-report-builder.md).</span></span>  
  
 <span data-ttu-id="3fc6d-130">Geschätzte Zeit zum Bearbeiten dieses Lernprogramms: 30 Minuten</span><span class="sxs-lookup"><span data-stu-id="3fc6d-130">Estimated time to complete this tutorial: 30 minutes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fc6d-131">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3fc6d-131">Requirements</span></span>  
 <span data-ttu-id="3fc6d-132">Weitere Informationen zu den Anforderungen finden Sie unter [Voraussetzungen für Tutorials &#40;Berichts-Generator&#41;](../reporting-services/report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="3fc6d-132">For information about requirements, see [Prerequisites for Tutorials &#40;Report Builder&#41;](../reporting-services/report-builder-tutorials.md).</span></span>  
  
##  <a name="1-create-a-map-with-a-polygon-layer-from-the-map-wizard"></a><a name="Map"></a><span data-ttu-id="3fc6d-133">1. Erstellen einer Karte mit einer Polygon Ebene im Karten-Assistenten</span><span class="sxs-lookup"><span data-stu-id="3fc6d-133">1. Create a Map with a Polygon Layer from the Map Wizard</span></span>  
 <span data-ttu-id="3fc6d-134">Führen Sie dem Bericht eine Karte aus dem Kartenkatalog hinzu.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-134">Add a map to your report from the map gallery.</span></span> <span data-ttu-id="3fc6d-135">Die Karte enthält eine Ebene, auf der die Countys im Bundesstaat New York angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-135">The map has one layer that displays the counties in New York state.</span></span> <span data-ttu-id="3fc6d-136">Die Form jedes Countys ist ein Polygon, das auf eingebetteten räumlichen Daten in der Karte aus dem Kartenkatalog basiert.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-136">The shape of each county is a polygon based on spatial data that is embedded in the map from the map gallery.</span></span>  
  
#### <a name="to-add-a-map-with-the-map-wizard-in-a-new-report"></a><span data-ttu-id="3fc6d-137">So fügen Sie mit dem Karten-Assistenten eine Karte in einem neuen Bericht hinzu</span><span class="sxs-lookup"><span data-stu-id="3fc6d-137">To add a map with the map wizard in a new report</span></span>  
  
1.  <span data-ttu-id="3fc6d-138">Klicken Sie auf **Start**, zeigen Sie auf **Programme**, zeigen Sie auf [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)] **Berichts-Generator**, und klicken Sie dann auf **Berichts-Generator**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-138">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../includes/sscurrentui-md.md)]**Report Builder**, and then click **Report Builder**.</span></span>  
  
     <span data-ttu-id="3fc6d-139">Das Dialogfeld Erste Schritte wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-139">The Getting Started dialog box appears.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3fc6d-140">Wenn das Dialogfeld "Getting Started" nicht angezeigt wird, klicken Sie auf der Schaltfläche "Berichts-Generator" auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-140">If the Getting Started dialog box does not appear, from the Report Builder button, click **New**.</span></span>  
  
2.  <span data-ttu-id="3fc6d-141">Vergewissern Sie sich im linken Bereich, dass der **Bericht** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-141">In the left pane, verify that **Report** is selected.</span></span>  
  
3.  <span data-ttu-id="3fc6d-142">Klicken Sie im rechten Bereich auf **Karten-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-142">In the right pane, click **Map Wizard**.</span></span>  
  
4.  <span data-ttu-id="3fc6d-143">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-143">Click **Create**.</span></span>  
  
5.  <span data-ttu-id="3fc6d-144">**Wählen Sie die Seite Quelle räumlicher Daten aus** , überprüfen Sie, ob **map Gallery** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-144">**Choose a source of spatial data** page, verify that **Map gallery** is selected.</span></span>  
  
6.  <span data-ttu-id="3fc6d-145">Erweitern Sie im Kartenkatalog unter **USA**den Eintrag **States by County** , und klicken Sie auf **New York**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-145">In the Map Gallery pane, expand **States by County** under **USA**, and click **New York**.</span></span>  
  
     <span data-ttu-id="3fc6d-146">Im Bereich "Kartenvorschau" wird die Karte der Countys in New York angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-146">The Map Preview pane displays the New York county map.</span></span>  
  
7.  <span data-ttu-id="3fc6d-147">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-147">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="3fc6d-148">Übernehmen Sie auf der Seite **Optionen für räumliche Daten und Kartenansicht auswählen** die Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-148">On the **Choose spatial data and map view options** page, accept the defaults.</span></span> <span data-ttu-id="3fc6d-149">Standardmäßig werden Kartenelemente aus einem Kartenkatalog automatisch in die Berichtsdefinition eingebettet.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-149">By default, map elements from a map gallery will automatically be embedded in the report definition.</span></span>  
  
9. <span data-ttu-id="3fc6d-150">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-150">Click **Next**.</span></span>  
  
10. <span data-ttu-id="3fc6d-151">Überprüfen Sie, ob auf der Seite **Kartenvisualisierung auswählen** der Eintrag **Standardkarte** ausgewählt ist, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-151">On the **Choose map visualization** page, verify **Basic Map** is selected, and click **Next**.</span></span>  
  
11. <span data-ttu-id="3fc6d-152">Aktivieren Sie auf der Seite **Farbdesign und Datenvisualisierung auswählen** die Option **Bezeichnungen anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="3fc6d-152">On the **Choose color theme and data visualization** page, select the **Display labels** option.</span></span>  
  
12. <span data-ttu-id="3fc6d-153">Falls aktiviert, deaktivieren Sie die Option **Einfarbige Karte** .</span><span class="sxs-lookup"><span data-stu-id="3fc6d-153">If it is selected, clear the **Single color map** option.</span></span>  
  
13. <span data-ttu-id="3fc6d-154">Klicken Sie in der Dropdown Liste **Datenfeld** auf #COUNTYNAME.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-154">From the **Data field** drop-down list, click #COUNTYNAME.</span></span> <span data-ttu-id="3fc6d-155">Im Kartenvorschaubereich im Assistenten werden die folgenden Elemente angezeigt:</span><span class="sxs-lookup"><span data-stu-id="3fc6d-155">The Map Preview pane in the wizard displays the following items:</span></span>  
  
    -   <span data-ttu-id="3fc6d-156">Ein Titel mit dem Text **Kartentitel**</span><span class="sxs-lookup"><span data-stu-id="3fc6d-156">A title with the text **Map Title**.</span></span>  
  
    -   <span data-ttu-id="3fc6d-157">Eine Karte der Countys in New York, in der jedes County mit einer anderen Farbe dargestellt und der Name des Countys angezeigt wird, sofern er über den Countybereich passt</span><span class="sxs-lookup"><span data-stu-id="3fc6d-157">A map that displays counties in New York where each county is a different color and the county name appears wherever it fits over the county area.</span></span>  
  
    -   <span data-ttu-id="3fc6d-158">Eine Legende, die einen Titel und eine Liste von Elementen von 1 bis 5 enthält.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-158">A legend that contains a title and a list of items 1 through 5.</span></span>  
  
    -   <span data-ttu-id="3fc6d-159">Eine Farbskala, die die Werte von 0 bis 160 und keine Farbe enthält.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-159">A color scale that contains values 0 to 160 and no color.</span></span>  
  
    -   <span data-ttu-id="3fc6d-160">Eine Entfernungsskala, auf der Kilometer (km) und Meilen (mi) angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="3fc6d-160">A distance scale that displays kilometers (km) and miles (mi).</span></span>  
  
14. <span data-ttu-id="3fc6d-161">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-161">Click **Finish**.</span></span>  
  
     <span data-ttu-id="3fc6d-162">Die Karte wird der Entwurfsoberfläche hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-162">The map is added to the design surface.</span></span>  
  
15. <span data-ttu-id="3fc6d-163">Klicken Sie auf die Karte, um Sie auszuwählen und den Bereich **Karten Ebenen**anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-163">Click the map to select it and display the **Map Layers Pane**.</span></span> <span data-ttu-id="3fc6d-164">Im Bereich **Karten Ebenen** wird eine Polygon Ebene vom Ebenentyp **eingebettet**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-164">The **Map Layers Pane** shows one polygon layer of layer type **Embedded**.</span></span> <span data-ttu-id="3fc6d-165">Jedes County ist ein eingebettetes Kartenelement auf dieser Ebene.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-165">Each county is an embedded map element on this layer.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3fc6d-166">Wenn Sie den Bereich **Karten Ebenen** nicht sehen, wird er möglicherweise außerhalb der aktuellen Ansicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-166">If you do not see the **Map Layers** pane, it might be displayed outside your current view.</span></span> <span data-ttu-id="3fc6d-167">Verwenden Sie die Bildlaufleiste am unteren Rand des Entwurfsansichtsfensters, um die Ansicht zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-167">Use the scroll bar at the bottom of the Design view window to change your view.</span></span> <span data-ttu-id="3fc6d-168">Deaktivieren Sie alternativ auf der Registerkarte **Ansicht** die Option **Eigenschaften** oder **Berichtsdaten** , um eine weitere Entwurfs Oberfläche bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-168">Alternatively, in the **View** tab, clear the **Properties** or the **Report Data** option to provide more design surface area.</span></span>  
  
16. <span data-ttu-id="3fc6d-169">Klicken Sie mit der rechten Maustaste auf den Karten Titel, und klicken Sie dann auf **Titel Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-169">Right-click the map title, and then click **Title Properties**.</span></span>  
  
17. <span data-ttu-id="3fc6d-170">Ersetzen Sie den Titeltext **durch Umsätze nach Geschäft**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-170">Replace the title text with **Sales by Store**.</span></span>  
  
18. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
19. <span data-ttu-id="3fc6d-171">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-171">Preview the report.</span></span>  
  
 <span data-ttu-id="3fc6d-172">Im gerenderten Bericht werden der Berichtstitel, der Kartentitel, die Karte und die Entfernungsskala angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-172">The rendered report displays the map title, the map, and the distance scale.</span></span> <span data-ttu-id="3fc6d-173">Die Countys befinden sich auf einer Polygonebene der Karte.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-173">The counties are on a map polygon layer.</span></span> <span data-ttu-id="3fc6d-174">Alle Countys werden als Polygone mit unterschiedlichen Farben aus einer Farbpalette dargestellt, die Farben sind jedoch keinen Daten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-174">Each county is a polygon that varies by color from a color palette, but the colors are not associated with any data.</span></span> <span data-ttu-id="3fc6d-175">Auf der Entfernungsskala werden Entfernungen sowohl in Kilometern als auch in Meilen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-175">The distance scale displays distances in both kilometers and miles.</span></span>  
  
 <span data-ttu-id="3fc6d-176">Die Kartenlegende und die Farbskala werden noch nicht angezeigt, da den Countys noch keine analytischen Daten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-176">The map legend and color scale do not yet appear because there is no analytical data associated with each county.</span></span> <span data-ttu-id="3fc6d-177">Sie fügen später in diesem Lernprogramm analytische Daten hinzu.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-177">You will add analytical data later in this tutorial.</span></span>  
  
##  <a name="2-add-a-map-point-layer-to-display-store-locations"></a><a name="PointLayer"></a><span data-ttu-id="3fc6d-178">2. Hinzufügen einer Karten Punkt Ebene, um Geschäftsstandorte anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="3fc6d-178">2. Add a Map Point Layer to Display Store Locations</span></span>  
 <span data-ttu-id="3fc6d-179">Fügen Sie mithilfe des Kartenebenen-Assistenten eine Punktebene hinzu, die den Standort von Geschäften anzeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-179">Use the map layer wizard to add a point layer that displays the locations of stores.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3fc6d-180">In diesem Lernprogramm sind die Datenwerte in der Abfrage enthalten, sodass keine externe Datenquelle benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-180">In this tutorial, the query contains the data values, so that it does not need an external data source.</span></span> <span data-ttu-id="3fc6d-181">Die Abfrage ist daher relativ lang.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-181">This makes the query quite long.</span></span> <span data-ttu-id="3fc6d-182">In einer Geschäftsumgebung wären die Daten nicht in der Abfrage enthalten.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-182">In a business environment, a query would not contain the data.</span></span> <span data-ttu-id="3fc6d-183">Dieses Szenario dient nur zu Lernzwecken.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-183">This is for learning purposes only.</span></span>  
  
#### <a name="to-add-a-point-layer-based-on-a-sql-server-spatial-query"></a><span data-ttu-id="3fc6d-184">So fügen Sie eine Punktebene auf Grundlage eines SQL Server-Abfrage nach räumlichen Daten hinzu</span><span class="sxs-lookup"><span data-stu-id="3fc6d-184">To add a point layer based on a SQL Server spatial query</span></span>  
  
1.  <span data-ttu-id="3fc6d-185">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-185">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="3fc6d-186">Doppelklicken Sie auf die Karte, um den Bereich **Kartenebenen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-186">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="3fc6d-187">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Assistent für neue Ebenen**![rs_IconMapLayerWizard](../../2014/tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard").</span><span class="sxs-lookup"><span data-stu-id="3fc6d-187">On the toolbar, click the **New layer wizard** button ![rs_IconMapLayerWizard](../../2014/tutorials/media/rs-iconmaplayerwizard.gif "rs_IconMapLayerWizard").</span></span>  
  
3.  <span data-ttu-id="3fc6d-188">Wählen Sie auf der Seite **Quelle räumlicher Daten auswählen** den Eintrag **SQL Server-Abfrage nach räumlichen Daten**aus, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-188">On the **Choose a source of spatial data** page, select **SQL Server spatial query**, and click **Next**.</span></span>  
  
4.  <span data-ttu-id="3fc6d-189">Klicken Sie auf der Seite **DataSet mit SQL Server räumlichen Daten auswählen** auf **neues Dataset mit SQL Server räumlichen Daten hinzufügen**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-189">On the **Choose a dataset with SQL Server spatial data** page, click **Add a new dataset with SQL Server spatial data**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="3fc6d-190">Wählen Sie auf der Seite **Verbindung mit einer SQL Server-Datenquelle für räumliche Daten auswählen** eine vorhandene Datenquelle aus, oder navigieren Sie zum Berichtsserver, und wählen Sie eine Datenquelle aus.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-190">On the **Choose a connection to a SQL Server spatial data source** page, select an existing data source or browse to the report server and select a data source.</span></span>  
  
6.  <span data-ttu-id="3fc6d-191">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-191">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="3fc6d-192">Klicken Sie auf der Seite Abfrage entwerfen auf **als Text bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-192">On the Design a Query page, click **Edit as Text**.</span></span>  
  
8.  <span data-ttu-id="3fc6d-193">Fügen Sie den folgenden Text in den Abfragebereich ein:</span><span class="sxs-lookup"><span data-stu-id="3fc6d-193">Paste the following text in the query pane:</span></span>  
  
    ```  
    Select 114 as StoreKey, 'Contoso Albany Store' as StoreName, 1125 as SellingArea, 'Albany' as City, 'Albany' as County,   
     CAST(1000000 as money) as Sales, CAST('POINT(-73.7472924218681 42.6564617079878)' as geography) AS SpatialLocation  
    UNION ALL SELECT 115 AS StoreKey, 'Contoso New York No.1 Store' AS  StoreName, 500 as SellingArea, 'New York' AS City, 'New York City' as County,  
     CAST('2000000' as money) as Sales, CAST('POINT(-73.9922069374483 40.7549638237402)' as geography) AS SpatialLocation  
    UNION ALL Select 116 as StoreKey, 'Contoso Rochester No.1 Store' as StoreName, 462 as SellingArea, 'Rochester' as City,  'Monroe' as County,    
     CAST(3000000 as money) as Sales, CAST('POINT(-77.624041566786 43.1547066024338)' as geography)  AS SpatialLocation  
    UNION ALL Select 117 as StoreKey, 'Contoso New York No.2 Store' as StoreName, 700 as SellingArea, 'New York' as City,'New York City' as County,    
      CAST(4000000 as money) as Sales, CAST('POINT(-73.9712488 40.7830603)' as geography) AS SpatialLocation  
    UNION ALL Select 118 as StoreKey, 'Contoso Syracuse Store' as StoreName, 680 as SellingArea, 'Syracuse' as City, 'Onondaga' as County,  
     CAST(5000000 as money) as Sales, CAST('POINT(-76.1349120532546 43.0610223535974)' as geography) AS SpatialLocation  
    UNION ALL Select 120 as StoreKey, 'Contoso Plattsburgh Store' as StoreName, 560 as SellingArea, 'Plattsburgh' as City,  'Clinton' as County,  
     CAST(6000000 as money) as Sales, CAST('POINT(-73.4728622833178 44.7028831413324)' as geography) AS SpatialLocation  
    UNION ALL Select 121 as StoreKey, 'Contoso Brooklyn Store' as StoreName, 1125 as SellingArea, 'Brooklyn' as City, 'New York City' as County,  
     CAST(7000000 as money) as Sales, CAST('POINT (-73.9638533447143 40.6785123489351)' as geography) AS SpatialLocation  
    UNION ALL Select 122 as StoreKey, 'Contoso Oswego Store' as StoreName, 500 as SellingArea, 'Oswego' as City, 'Oswego' as County,    
     CAST(8000000 as money) as Sales, CAST('POINT(-76.4602850815536 43.4353224527794)' as geography) AS SpatialLocation  
    UNION ALL Select 123 as StoreKey, 'Contoso Ithaca Store' as StoreName, 460 as SellingArea, 'Ithaca' as City, 'Tompkins' as County,  
     CAST(9000000 as money) as Sales, CAST('POINT(-76.5001866085881 42.4310489934743)' as geography) AS SpatialLocation  
    UNION ALL Select 124 as StoreKey, 'Contoso Rochester No.2 Store' as StoreName, 700 as SellingArea, 'Rochester' as City, 'Monroe' as County,    
     CAST(100000 as money) as Sales, CAST('POINT(-77.6240415667866 43.1547066024338)' as geography) AS SpatialLocation  
    UNION ALL Select 125 as StoreKey, 'Contoso Queens Store' as StoreName, 700 as SellingArea,'Queens' as City, 'New York City' as County,  
     CAST(500000 as money) as Sales, CAST('POINT(-73.7930979029883 40.7152781765927)' as geography) AS SpatialLocation  
    UNION ALL Select 126 as StoreKey, 'Contoso Elmira Store' as StoreName, 680 as SellingArea, 'Elmira' as City, 'Chemung' as County,  
     CAST(800000 as money) as Sales, CAST('POINT(-76.7397414783301 42.0736492742663)' as geography) AS SpatialLocation  
    UNION ALL Select 127 as StoreKey, 'Contoso Poestenkill Store' as StoreName, 455 as SellingArea, 'Poestenkill' as City, 'Rensselaer' as County,    
    CAST(1500000 as money) as Sales, CAST('POINT(-73.5626737425063 42.6940551238618)' as geography) AS SpatialLocation  
    ```  
  
9. <span data-ttu-id="3fc6d-194">Klicken Sie auf der Symbolleiste des Abfrage-Designers auf **Ausführen** (**!**).</span><span class="sxs-lookup"><span data-stu-id="3fc6d-194">On the query designer toolbar, click **Run** (**!**).</span></span>  
  
     <span data-ttu-id="3fc6d-195">Das Resultset enthält sieben Spalten: "StoreKey", "StoreName", "SellingArea", "City", "County", "Sales" und "SpatialLocation".</span><span class="sxs-lookup"><span data-stu-id="3fc6d-195">The result set displays seven columns: StoreKey, StoreName, SellingArea, City, County, Sales, and SpatialLocation.</span></span> <span data-ttu-id="3fc6d-196">Diese Daten stellen einen Satz von Geschäften im Bundesstaat New York dar, in denen Verbrauchsgüter verkauft werden.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-196">This data represents a set of stores in New York State that sell consumer goods.</span></span> <span data-ttu-id="3fc6d-197">Jede Zeile im Resultset enthält eine Geschäfts-ID, den Geschäftsnamen, die für die Produkte verfügbare Ausstellfläche, den Ort und das County, in dem sich das Geschäft befindet, den Jahresumsatz und die räumliche Position in Längen- und Breitengrad.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-197">Each row in the result set contains a store identifier, store name, the area available for product display, the city and county where the store is located, the sales total, and the spatial location in longitude and latitude.</span></span> <span data-ttu-id="3fc6d-198">Die Ausstellfläche liegt zwischen 455 Quadratfuß und 1125 Quadratfuß.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-198">The display area ranges from 455 square feet to 1125 square feet.</span></span>  
  
10. <span data-ttu-id="3fc6d-199">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-199">Click **Next**.</span></span>  
  
     <span data-ttu-id="3fc6d-200">Das Berichtsdataset mit dem Namen "DataSet1" wird für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-200">The report dataset named DataSet1 is created for you.</span></span> <span data-ttu-id="3fc6d-201">Nachdem Sie den Assistenten abgeschlossen haben, können Sie die zugehörige Feldauflistung in den Berichtsdaten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-201">After you complete the wizard, you can use the Report Data to its field collection.</span></span>  
  
11. <span data-ttu-id="3fc6d-202">Überprüfen Sie auf der Seite **Optionen für räumliche Daten und Kartenansicht auswählen** , ob das **räumliche Feld** ist `SpatialLocation` und der **Ebenentyp** **Punkt**ist.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-202">On the **Choose a spatial data and map view options** page, verify that the **Spatial field** is `SpatialLocation` and that the **Layer type** is **Point**.</span></span> <span data-ttu-id="3fc6d-203">Übernehmen Sie die anderen Standardwerte auf dieser Seite.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-203">Accept the other defaults on this page.</span></span>  
  
     <span data-ttu-id="3fc6d-204">In der Kartensicht werden Kreise angezeigt, die den Standort jedes Geschäfts markieren.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-204">The map view displays circles that mark the location of each store.</span></span>  
  
12. <span data-ttu-id="3fc6d-205">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-205">Click **Next**.</span></span>  
  
13. <span data-ttu-id="3fc6d-206">Geben Sie einen Kartentyp an, in dem nach analytischen Daten variierende Marker angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-206">Specify a map type that displays markers that vary by analytic data.</span></span> <span data-ttu-id="3fc6d-207">Klicken Sie auf der Seite Karten Visualisierung auswählen auf **analytische markerkarte**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-207">On the Choose map visualization page, click **Analytical Marker Map**, and then click **Next**.</span></span>  
  
14. <span data-ttu-id="3fc6d-208">Klicken Sie auf der Seite **analytisches Dataset auswählen** auf DataSet1.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-208">On the **Choose the analytical dataset** page, click DataSet1.</span></span> <span data-ttu-id="3fc6d-209">Dieses Dataset enthält sowohl analytische Daten als auch räumliche Daten, die auf der neuen Punktebene angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-209">This dataset contains both analytical data and spatial data that will be displayed on the new point layer.</span></span>  
  
15. <span data-ttu-id="3fc6d-210">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-210">Click **Next**.</span></span>  
  
16. <span data-ttu-id="3fc6d-211">Deaktivieren Sie auf der Seite **Farbdesign und Datenvisualisierung auswählen** die Option **Markerfarben zum Visualisieren von Daten verwenden** , und aktivieren Sie dann die Option **Markertypen zum Anzeigen von Daten verwenden**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-211">On the **Choose color theme and data visualization** page, clear the **Use marker colors to visualize data** option, and then select the option **Use marker types to visualize data**.</span></span>  
  
17. <span data-ttu-id="3fc6d-212">Wählen Sie unter **Datenfeld**aus, `[Sum(SellingArea)]` um die Markertypen nach der Größe des Bereichs zu verändern, den ein Speicher für die Anzeige der Produkte reserviert.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-212">In **Data field**, select `[Sum(SellingArea)]` to vary marker types by the size of the area a store sets aside to display the products.</span></span>  
  
18. <span data-ttu-id="3fc6d-213">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-213">Click **Finish**.</span></span>  
  
     <span data-ttu-id="3fc6d-214">Die Kartenebene wird dem Bericht hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-214">The map layer is added to the report.</span></span> <span data-ttu-id="3fc6d-215">Auf der Legende werden Markertypen basierend auf den SellingArea-Werten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-215">The legend displays marker types based on SellingArea values.</span></span>  
  
     <span data-ttu-id="3fc6d-216">Doppelklicken Sie auf die Karte, um den Bereich **Kartenebenen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-216">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="3fc6d-217">Im Bereich **Kartenebenen** wird eine neue Ebene PointLayer1 mit dem räumlichen Datenquellentyp **DataRegion**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-217">The **Map Layer** pane displays a new layer, PointLayer1, with spatial data source type **DataRegion**.</span></span>  
  
19. <span data-ttu-id="3fc6d-218">Fügen Sie einen Legendentitel hinzu.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-218">Add a legend title.</span></span> <span data-ttu-id="3fc6d-219">Klicken Sie mit der rechten Maustaste auf den Legenden Titel, und klicken Sie dann auf **Legenden Titel Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-219">Right-click the legend title, and then click **Legend Title Properties**.</span></span>  
  
20. <span data-ttu-id="3fc6d-220">Löschen Sie den Titel, und geben Sie **Anzeigebereich (quadratische Füße)** ein.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-220">Delete the title, and type **Display Area (Square Feet)**.</span></span>  
  
21. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
22. <span data-ttu-id="3fc6d-221">Zeigen Sie die vom Assistenten festgelegten Standardwerte an.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-221">View the default values that were set by the wizard.</span></span> <span data-ttu-id="3fc6d-222">Klicken Sie im Bereich **Karten Ebenen**mit der rechten Maustaste auf die Punkt Ebene, und klicken Sie dann auf **Regel für Markertyp**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-222">In the **Map Layers Pane**, right-click the point layer, and then click **Marker Type Rule**.</span></span>  
  
     <span data-ttu-id="3fc6d-223">Auf der Registerkarte **Allgemein** werden die Marker in der Reihenfolge aufgelistet, in der Sie in der Legende angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-223">On the **General** tab, the markers are listed in the order in which they appear in the legend.</span></span> <span data-ttu-id="3fc6d-224">Auf der Registerkarte **Verteilung** beträgt die Anzahl der Unterbereiche 5.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-224">On the **Distribution** tab, the number of subranges is 5.</span></span> <span data-ttu-id="3fc6d-225">Auf der Registerkarte **Legende** wird der Legenden Text so festgelegt, dass der Start-und Endwert in jedem Bereich angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-225">On the **Legend** tab, the legend text is set to display the start and end value in each range.</span></span>  
  
23. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
24. <span data-ttu-id="3fc6d-226">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-226">Preview the report.</span></span>  
  
 <span data-ttu-id="3fc6d-227">Auf der Karte werden die Standorte von Geschäften im Bundesstaat New York angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-227">The map displays the locations of stores in New York state.</span></span> <span data-ttu-id="3fc6d-228">Der Markertyp für jedes Geschäft basiert auf der Aufstellfläche.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-228">The marker type for each store is based on the display area.</span></span> <span data-ttu-id="3fc6d-229">Fünf Bereiche wurden automatisch für die Aufstellfläche berechnet.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-229">Five ranges of display area were automatically calculated for you.</span></span>  
  
##  <a name="3-add-a-map-line-layer-to-display-a-route"></a><a name="LineLayer"></a><span data-ttu-id="3fc6d-230">3. Hinzufügen einer Karten Linien Ebene, um eine Route anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="3fc6d-230">3. Add a Map Line Layer to Display a Route</span></span>  
 <span data-ttu-id="3fc6d-231">Fügen Sie mithilfe des Kartenebenen-Assistenten eine Kartenebene hinzu, die eine Route zwischen zwei Geschäften anzeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-231">Use the map layer wizard to add a map layer that displays a route between two stores.</span></span> <span data-ttu-id="3fc6d-232">In diesem Lernprogramm wird der Weg für drei Geschäftsstandorte erstellt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-232">In this tutorial, the path is created from three store locations.</span></span> <span data-ttu-id="3fc6d-233">In einer Geschäftsanwendung könnte es sich bei dem Weg um die beste Route zwischen Geschäften handeln.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-233">In a business application, the path might be the best route between stores.</span></span>  
  
#### <a name="to-add-a-line-layer-to-map"></a><span data-ttu-id="3fc6d-234">So fügen Sie der Karte eine Linienebene hinzu</span><span class="sxs-lookup"><span data-stu-id="3fc6d-234">To add a line layer to map</span></span>  
  
1.  <span data-ttu-id="3fc6d-235">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-235">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="3fc6d-236">Doppelklicken Sie auf die Karte, um den Bereich **Kartenebenen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-236">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="3fc6d-237">Klicken Sie auf der Symbolleiste auf **Assistent für neue Ebenen**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-237">On the toolbar, click **New layer wizard**.</span></span>  
  
3.  <span data-ttu-id="3fc6d-238">Wählen Sie auf der Seite **Quelle räumlicher Daten auswählen** **SQL Server räumliche Abfrage** aus, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-238">On the **Choose a source of spatial data** page, select **SQL Server spatial query** and click **Next**.</span></span>  
  
4.  <span data-ttu-id="3fc6d-239">Klicken Sie auf der Seite **Dataset mit räumlichen SQL Server-Daten auswählen** auf **Neues Dataset mit räumlichen SQL Server-Daten hinzufügen** anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-239">On the **Choose a dataset with SQL Server spatial data** page, click **Add a new dataset with SQL Server spatial data** and click **Next**.</span></span>  
  
5.  <span data-ttu-id="3fc6d-240">Wählen Sie unter **Verbindung mit einer SQL Server räumliche Datenquelle auswählen**die Datenquelle DataSource1 aus, die Sie im ersten Verfahren erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-240">On the **Choose a connection to a SQL Server spatial data source**, select DataSource1, the data source that you created in the first procedure.</span></span>  
  
6.  <span data-ttu-id="3fc6d-241">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-241">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="3fc6d-242">Klicken Sie auf der Seite **Abfrage entwerfen** auf **als Text bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-242">On the **Design a Query** page, click **Edit as Text**.</span></span> <span data-ttu-id="3fc6d-243">Der Abfrage-Designer wechselt in den textbasierten Modus.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-243">The query designer switches to text-based mode.</span></span>  
  
8.  <span data-ttu-id="3fc6d-244">Fügen Sie den folgenden Text in den Abfragebereich ein:</span><span class="sxs-lookup"><span data-stu-id="3fc6d-244">Paste the following text in the query pane:</span></span>  
  
    ```  
    SELECT N'Path' AS Name, CAST('LINESTRING(  
       -76.5001866085881 42.4310489934743,  
       -76.4602850815536 43.4353224527794,  
       -73.4728622833178 44.7028831413324)' AS geography) as Route  
    ```  
  
9. <span data-ttu-id="3fc6d-245">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-245">Click **Next**.</span></span>  
  
     <span data-ttu-id="3fc6d-246">Auf der Karte wird ein Weg angezeigt, der drei Geschäfte verbindet.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-246">A path appears on the map that connects three stores.</span></span>  
  
10. <span data-ttu-id="3fc6d-247">Überprüfen Sie auf der Seite **Optionen für räumliche Daten und Kartenansicht auswählen** , ob für **Räumliches Feld** der Wert **Route** und für **Ebenentyp** der Wert **Linie**ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-247">On the **Choose spatial data and map view options** page, verify that the **Spatial field** is **Route** and that the **Layer type** is **Line**.</span></span> <span data-ttu-id="3fc6d-248">Übernehmen Sie die anderen Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-248">Accept the other defaults.</span></span>  
  
     <span data-ttu-id="3fc6d-249">In der Kartensicht wird ein Weg von einem Geschäft im nördlichen Teil des Bundesstaats New York zu einem Geschäft im südlichen Teil des Bundesstaats New York angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-249">The map view displays a path from a store in the northern part of New York state to a store in the southern part of New York state.</span></span>  
  
11. <span data-ttu-id="3fc6d-250">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-250">Click **Next**.</span></span>  
  
12. <span data-ttu-id="3fc6d-251">Klicken Sie auf der Seite **Kartenvisualisierung auswählen** auf **Standardkarte (Linien)** und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-251">On the **Choose map visualization** page, click **Basic Line Map**, and then click **Next**.</span></span>  
  
13. <span data-ttu-id="3fc6d-252">Aktivieren Sie unter **Farbdesign und Datenvisualisierung auswählen**die Option **Einfarbige Karte**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-252">On the **Choose color theme and data visualization**, select the option **Single color map**.</span></span> <span data-ttu-id="3fc6d-253">Der Weg wird mit einer einzelnen Farbe angezeigt, die auf dem ausgewählten Design basiert.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-253">The path appears as a single color based on the selected theme.</span></span>  
  
14. <span data-ttu-id="3fc6d-254">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-254">Click **Finish**.</span></span>  
  
 <span data-ttu-id="3fc6d-255">In der Karte wird eine neue Linien Ebene mit **DataSet**vom Typ räumlicher Datenquelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-255">The map displays a new line layer with spatial data source type **DataSet**.</span></span> <span data-ttu-id="3fc6d-256">In diesem Beispiel stammen die räumlichen Daten aus einem Dataset, aber der Linie sind keine analytischen Daten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-256">In this example, the spatial data comes from a dataset but no analytical data is associated with the line.</span></span>  
  
##  <a name="4-add-a-bing-maps-tile-background"></a><a name="TileLayer"></a><span data-ttu-id="3fc6d-257">4. Hinzufügen eines Kachel Hintergrunds für die Kachel</span><span class="sxs-lookup"><span data-stu-id="3fc6d-257">4. Add a Bing Maps Tile Background</span></span>  
 <span data-ttu-id="3fc6d-258">Fügen Sie eine Kartenebene hinzu, die einen Bing Maps-Kachelhintergrund anzeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-258">Add a map layer that displays a Bing Maps tile background.</span></span>  
  
#### <a name="to-add-a-virtual-earth-tile-background"></a><span data-ttu-id="3fc6d-259">So fügen Sie einen Virtual Earth-Kachelhintergrund hinzu</span><span class="sxs-lookup"><span data-stu-id="3fc6d-259">To add a Virtual Earth tile background</span></span>  
  
1.  <span data-ttu-id="3fc6d-260">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-260">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="3fc6d-261">Doppelklicken Sie auf die Karte, um den Bereich **Kartenebenen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-261">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="3fc6d-262">Klicken Sie auf der Symbolleiste auf **Ebene hinzufügen**![rs_IconMapAddLayer](../../2014/tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer").</span><span class="sxs-lookup"><span data-stu-id="3fc6d-262">On the toolbar, click **Add Layer**![rs_IconMapAddLayer](../../2014/tutorials/media/rs-iconmapaddlayer.gif "rs_IconMapAddLayer").</span></span>  
  
3.  <span data-ttu-id="3fc6d-263">Klicken Sie in der Dropdownliste auf **Kachelebene**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-263">From the drop-down list, click **Tile Layer**.</span></span>  
  
     <span data-ttu-id="3fc6d-264">Die letzte Ebene im Bereich **Kartenebene** ist TileLayer1.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-264">The last layer in the **Map Layer** pane is TileLayer1.</span></span> <span data-ttu-id="3fc6d-265">Standardmäßig zeigt die Kachelebene das Straßenkartenformat an.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-265">By default, the tile layer displays the road map style.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3fc6d-266">Sie können auch im Assistenten auf der Seite **Optionen für räumliche Daten und Kartenansicht auswählen** eine Kachelebene hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-266">In the wizard, you can also add a tile layer on the **Choose spatial data and map view options** page.</span></span> <span data-ttu-id="3fc6d-267">Wählen Sie dazu **Bing Maps-Hintergrund für diese Kartenansicht hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-267">To do this, select **Add a Bing Maps background for this map view**.</span></span> <span data-ttu-id="3fc6d-268">In einem gerenderten Bericht zeigt der Kachelhintergrund Bing Maps-Kacheln für den aktuellen Kartenviewport-Mittelpunkt und die aktuelle Zoomstufe an.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-268">In a rendered report, the tile background displays Bing Maps tiles for the current map viewport center and zoom level.</span></span>  
  
4.  <span data-ttu-id="3fc6d-269">Klicken Sie in "TileLayer1" auf den Pfeil nach unten, und klicken Sie dann auf **Kachel Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-269">Click the down arrow on TileLayer1, and then click **Tile Properties**.</span></span>  
  
5.  <span data-ttu-id="3fc6d-270">Wählen Sie unter **Typ**die Option **Luftbild**aus.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-270">In **Type**, select **Aerial**.</span></span> <span data-ttu-id="3fc6d-271">Das Luftbild enthält keinen Text.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-271">The aerial view does not contain text.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
##  <a name="5-make-a-layer-transparent"></a><a name="Transparent"></a><span data-ttu-id="3fc6d-272">5. eine Ebene transparent machen</span><span class="sxs-lookup"><span data-stu-id="3fc6d-272">5. Make a Layer Transparent</span></span>  
 <span data-ttu-id="3fc6d-273">Sie können die Reihenfolge von Ebenen und die Transparenz jeder Ebene anpassen, um die Elemente auf einer Ebene durch andere Ebenen durchscheinen zu lassen und den gewünschten Transparenzeffekt zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-273">To let the items on one layer show through another layer, you can adjust the order of layers and the transparency of each layer to get the effect that you want.</span></span>  
  
#### <a name="to-set-the-transparency-of-a-layer"></a><span data-ttu-id="3fc6d-274">So legen Sie die Transparenz einer Ebene fest</span><span class="sxs-lookup"><span data-stu-id="3fc6d-274">To set the transparency of a layer</span></span>  
  
1.  <span data-ttu-id="3fc6d-275">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-275">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="3fc6d-276">Doppelklicken Sie auf die Karte, um den Bereich **Kartenebenen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-276">Double-click the map to display the **Map Layer** pane.</span></span>  
  
3.  <span data-ttu-id="3fc6d-277">Klicken Sie in PolygonLayer1 auf den Pfeil nach unten, und klicken Sie dann auf **ebenendungen**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-277">Click the down arrow on PolygonLayer1, and then click **Layer Data**.</span></span> <span data-ttu-id="3fc6d-278">Das Dialogfeld **Polygonebeneneigenschaften von Karten** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-278">The **Map Polygon Layer Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="3fc6d-279">Klicken Sie auf **Sichtbarkeit**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-279">Click **Visibility**.</span></span>  
  
5.  <span data-ttu-id="3fc6d-280">Geben Sie unter **Transparenz (%)** den Typ **30**ein.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-280">In **Transparency (%)**, type **30**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
 <span data-ttu-id="3fc6d-281">Auf der Entwurfsoberfläche werden die Countys halbtransparent dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-281">The design surface displays the counties as semi-transparent.</span></span>  
  
##  <a name="6-vary-county-color-based-on-sales"></a><a name="Vary"></a><span data-ttu-id="3fc6d-282">6. verändern der Bezirks Farbe basierend auf den Verkäufen</span><span class="sxs-lookup"><span data-stu-id="3fc6d-282">6. Vary County Color Based on Sales</span></span>  
 <span data-ttu-id="3fc6d-283">Jedes County in der Polygonebene hat eine andere Farbe, da der Berichtsprozessor automatisch auf der Grundlage des Designs, das Sie auf der letzten Seite des Karten-Assistenten ausgewählt haben, einen Farbwert aus der Farbpalette zuweist.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-283">Each county on the polygon layer has a different color because the report processor automatically assigns a color value from the color palette based on the theme that you chose on the last page of the map wizard.</span></span>  
  
 <span data-ttu-id="3fc6d-284">In den folgenden Schritten geben Sie eine Farbregel an, um bestimmte Farben einem Bereich von Geschäftsumsätzen für jedes County zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-284">In the following steps, specify a color rule to associate specific colors with a range of store sales for each county.</span></span> <span data-ttu-id="3fc6d-285">Die Farben rot, gelb und grün geben relativ hohe, mittlere bzw. niedrige Umsätze an.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-285">The colors red-yellow-green indicate relative high-middle-low sales.</span></span> <span data-ttu-id="3fc6d-286">Formatieren Sie die Farbskala, um Währungswerte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-286">Format the color scale to show currency.</span></span> <span data-ttu-id="3fc6d-287">Zeigen Sie die Jahresumsatzbereiche in einer neuen Legende an.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-287">Display the annual sales ranges in a new legend.</span></span> <span data-ttu-id="3fc6d-288">Verwenden Sie für Countys ohne Geschäfte keine Farbe, um anzuzeigen, dass keine zugeordneten Daten vorliegen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-288">For counties that do not contain stores, use no color to show that there is no associated data.</span></span>  
  
###  <a name="6a-build-a-relationship-between-spatial-and-analytical-data"></a><a name="Relationship"></a><span data-ttu-id="3fc6d-289">6a.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-289">6a.</span></span> <span data-ttu-id="3fc6d-290">Erstellen einer Beziehung zwischen räumlichen und analytischen Daten</span><span class="sxs-lookup"><span data-stu-id="3fc6d-290">Build a Relationship between Spatial and Analytical Data</span></span>  
 <span data-ttu-id="3fc6d-291">Um die Countyformen auf der Grundlage analytischer Daten farblich zu unterscheiden, müssen Sie zuerst die analytischen Daten den räumlichen Daten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-291">To vary the county shapes by color based on analytical data, you first must associate the analytical data with the spatial data.</span></span> <span data-ttu-id="3fc6d-292">In diesem Lernprogramm verwenden Sie zu diesem Zweck den Countynamen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-292">In this tutorial, you will use the county name to match on.</span></span>  
  
##### <a name="to-build-a-relationship-between-spatial-data-and-analytical-data"></a><span data-ttu-id="3fc6d-293">So erstellen Sie eine Beziehung zwischen räumlichen Daten und analytischen Daten</span><span class="sxs-lookup"><span data-stu-id="3fc6d-293">To build a relationship between spatial data and analytical data</span></span>  
  
1.  <span data-ttu-id="3fc6d-294">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-294">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="3fc6d-295">Doppelklicken Sie auf die Karte, um den Bereich **Kartenebenen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-295">Double-click the map to display the **Map Layer** pane.</span></span>  
  
3.  <span data-ttu-id="3fc6d-296">Klicken Sie in PolygonLayer1 auf den Pfeil nach unten, und klicken Sie dann auf **ebenendungen**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-296">Click the down arrow on PolygonLayer1, and then click **Layer Data**.</span></span> <span data-ttu-id="3fc6d-297">Das Dialogfeld **Polygonebeneneigenschaften von Karten** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-297">The **Map Polygon Layer Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="3fc6d-298">Klicken Sie auf **Analytische Daten**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-298">Click **Analytical data**.</span></span>  
  
5.  <span data-ttu-id="3fc6d-299">Wählen Sie in der Dropdownliste den Eintrag "DataSet1" aus.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-299">From the drop-down list, select DataSet1.</span></span> <span data-ttu-id="3fc6d-300">Dieses Dataset wurde vom Assistenten erstellt, als Sie die Abfrage räumlicher Daten für die Countys angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-300">This dataset was created by the wizard when you specified the spatial data query for the counties.</span></span>  
  
6.  <span data-ttu-id="3fc6d-301">Klicken Sie unter zu Übereinstimmungs **Felder auf** **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-301">In **Fields to match on**, click **Add**.</span></span> <span data-ttu-id="3fc6d-302">Eine neue Zeile wird hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-302">A new row is added.</span></span>  
  
7.  <span data-ttu-id="3fc6d-303">Klicken Sie in **aus räumlichem DataSet**in der Dropdown Liste auf zählname.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-303">In **From spatial dataset**, from the drop-down list, click COUNTYNAME.</span></span>  
  
8.  <span data-ttu-id="3fc6d-304">Klicken Sie unter **aus analytisches DataSet**in der Dropdown Liste auf [County].</span><span class="sxs-lookup"><span data-stu-id="3fc6d-304">In **From analytical dataset**, from the drop-down list, click [County].</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
10. <span data-ttu-id="3fc6d-305">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-305">Preview the report.</span></span>  
  
 <span data-ttu-id="3fc6d-306">Durch die Angabe eines Übereinstimmungsfelds aus der räumlichen Datenquelle und aus dem analytischen Dataset kann der Berichtsprozessor analytische Daten auf Grundlage der Kartenelemente gruppieren.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-306">By specifying a match field from the spatial data source and from the analytical dataset, you enable the report processor to group analytical data based on the map elements.</span></span> <span data-ttu-id="3fc6d-307">Bei einem datengebundenen Kartenelement wird eine erfolgreiche Übereinstimmung für die von Ihnen angegebenen Werte erzielt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-307">A data-bound map element has a successful match for the values that you specified.</span></span>  
  
 <span data-ttu-id="3fc6d-308">Jedem County mit einem Geschäft ist eine Farbe zugeordnet, die auf der Farbpalette für das im Assistenten ausgewählte Format basiert.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-308">Each county that contains a store has a color that is based on the color palette for the style that you chose in the wizard.</span></span>  
  
###  <a name="6b-specify-color-rules-for-polygons"></a><a name="ColorRules"></a><span data-ttu-id="3fc6d-309">6B.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-309">6b.</span></span> <span data-ttu-id="3fc6d-310">Festlegen von Farbregeln für Polygone</span><span class="sxs-lookup"><span data-stu-id="3fc6d-310">Specify Color Rules for Polygons</span></span>  
 <span data-ttu-id="3fc6d-311">Zum Erstellen einer Regel, die die Farbe jedes Countys basierend auf dem Geschäftsumsatz verändert, müssen Sie die Bereichswerte, die Anzahl anzuzeigender Einteilungen innerhalb dieses Bereichs und die zu verwendenden Farben angeben.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-311">To create a rule that varies the color of each county based store sales, you must specify the range values, the number of divisions within that range that you want to display, and the colors to use.</span></span>  
  
##### <a name="to-specify-color-rules-for-all-polygons-that-have-associated-data"></a><span data-ttu-id="3fc6d-312">So geben Sie Farbregeln für alle Polygone mit zugeordneten Daten an</span><span class="sxs-lookup"><span data-stu-id="3fc6d-312">To specify color rules for all polygons that have associated data</span></span>  
  
1.  <span data-ttu-id="3fc6d-313">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-313">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="3fc6d-314">Klicken Sie in PolygonLayer1 auf den Pfeil nach unten, und klicken Sie dann auf **Polygon Farbregel**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-314">Click the down arrow on PolygonLayer1, and then click **Polygon Color Rule**.</span></span> <span data-ttu-id="3fc6d-315">Das Dialogfeld **Farbregeleigenschaften der Karte** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-315">The **Map Color Rules Properties** dialog box opens.</span></span> <span data-ttu-id="3fc6d-316">Beachten Sie, dass die Farbregeloption **Daten mithilfe der Farbpalette anzeigen** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-316">Notice that the color rule option **Visualize data by using color palette** is selected.</span></span> <span data-ttu-id="3fc6d-317">Diese Option wurde vom Assistenten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-317">This option was set by the wizard.</span></span>  
  
3.  <span data-ttu-id="3fc6d-318">Aktivieren Sie **Daten mithilfe von Farbbereichen anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-318">Select **Visualize data by using color ranges**.</span></span> <span data-ttu-id="3fc6d-319">Die Palettenoption wird durch die Optionen für Startfarbe, mittlere Farbe und Endfarbe ersetzt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-319">The palette option is replaced by start color, middle color, and end color options.</span></span>  
  
4.  <span data-ttu-id="3fc6d-320">Definieren Sie Bereichswerte für die Umsätze pro County.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-320">Define range values for sales per county.</span></span> <span data-ttu-id="3fc6d-321">Wählen Sie unter **Datenfeld**den Eintrag `[Sum(Sales)]`in der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-321">In **Data field**, from the drop-down list, select `[Sum(Sales)]`.</span></span>  
  
5.  <span data-ttu-id="3fc6d-322">Ändern Sie den Ausdruck wie folgt, um das Format zur Anzeige der Währung in Tausendern zu ändern: `=Sum(Fields!Sales.Value)/1000`</span><span class="sxs-lookup"><span data-stu-id="3fc6d-322">To change the format to display currency in thousands, change the expression to the following: `=Sum(Fields!Sales.Value)/1000`</span></span>  
  
6.  <span data-ttu-id="3fc6d-323">Ändern Sie **Startfarbe** in **Rot**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-323">Change **Start color** to **Red**.</span></span>  
  
7.  <span data-ttu-id="3fc6d-324">Ändern Sie **Endfarbe** in **Grün**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-324">Change **End color** to **Green**.</span></span>  
  
     <span data-ttu-id="3fc6d-325">**Rot** stellt niedrige Umsatzwerte dar, **Gelb** stellt mittlere Umsatzwerte dar, und **Grün** stellt hohe Umsatzwerte dar.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-325">**Red** represents low sales values, **Yellow** represents middle sales values, and **Green** represents high sales values.</span></span> <span data-ttu-id="3fc6d-326">Der Berichtsprozessor berechnet einen Bereich von Farben auf der Grundlage dieser Werte und der Optionen, die Sie auf der Seite **Verteilung** auswählen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-326">The report processor calculates a range of colors based on these values and the options that you choose on the **Distribution** page.</span></span>  
  
8.  <span data-ttu-id="3fc6d-327">Klicken Sie auf **Verteilung**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-327">Click **Distribution**.</span></span>  
  
9. <span data-ttu-id="3fc6d-328">Überprüfen Sie, ob der Verteilungstyp **Optimal**lautet.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-328">Verify that the distribution type is **Optimal**.</span></span> <span data-ttu-id="3fc6d-329">Für den Ausdruck aus Schritt 5 werden die Werte durch die optimale Verteilung in Teilbereiche aufgeteilt, deren Elementanzahl und Umfang jeweils gleich sind.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-329">For the expression from step 5, optimal distribution divides the values into subranges that balance the number of items in each range and the span for each range.</span></span>  
  
10. <span data-ttu-id="3fc6d-330">Übernehmen Sie die Standardwerte für andere Optionen auf dieser Seite.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-330">Accept the default values for other options on this page.</span></span> <span data-ttu-id="3fc6d-331">Wenn Sie den optimalen Verteilungstyp auswählen, wird die Anzahl der Teilbereiche bei der Berichtausführung berechnet.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-331">When you select the optimal distribution type, the number of subranges are calculated when the report runs.</span></span>  
  
11. <span data-ttu-id="3fc6d-332">Klicken Sie auf **Legende**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-332">Click **Legend**.</span></span>  
  
12. <span data-ttu-id="3fc6d-333">Überprüfen Sie, ob unter **Farbskalaoptionen**der Wert **In Farbskala anzeigen** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-333">In **Color scale options**, verify that **Show in color scale** is selected.</span></span>  
  
13. <span data-ttu-id="3fc6d-334">Wählen Sie unter **In dieser Legende anzeigen**in der Dropdownliste die Leerzeile aus.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-334">In **Show in this legend**, from the drop-down list, select the blank line.</span></span> <span data-ttu-id="3fc6d-335">Zurzeit zeigen Sie die Farbbereiche nur in der Farbskala an.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-335">For now, you will show the color ranges only in the color scale.</span></span>  
  
14. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
 <span data-ttu-id="3fc6d-336">Auf der Farbskala werden fünf Farben angezeigt: rot, orange, gelb, gelbgrün und grün.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-336">The color scale displays five colors: red, orange, yellow, yellow green, and green.</span></span> <span data-ttu-id="3fc6d-337">Jede Farbe stellt einen Umsatzbereich dar, der automatisch auf Grundlage der Umsätze nach County berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-337">Each color represents a sales range that is automatically calculated based on the sales by county.</span></span>  
  
###  <a name="6c-format-the-data-in-the-color-scale-as-currency"></a><a name="ColorScale"></a><span data-ttu-id="3fc6d-338">6C.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-338">6c.</span></span> <span data-ttu-id="3fc6d-339">Formatieren der Daten in der Farbskala als Währung</span><span class="sxs-lookup"><span data-stu-id="3fc6d-339">Format the Data in the Color Scale as Currency</span></span>  
 <span data-ttu-id="3fc6d-340">Für Daten wird standardmäßig ein allgemeines Format verwendet.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-340">By default, data has a general format.</span></span> <span data-ttu-id="3fc6d-341">Sie können benutzerdefinierte Formate anwenden.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-341">You can apply custom formats.</span></span>  
  
##### <a name="to-set-the-format-for-the-color-scale"></a><span data-ttu-id="3fc6d-342">So legen Sie das Format für die Farbskala fest</span><span class="sxs-lookup"><span data-stu-id="3fc6d-342">To set the format for the color scale</span></span>  
  
1.  <span data-ttu-id="3fc6d-343">Klicken Sie mit der rechten Maustaste auf die Farbskala, und klicken Sie dann auf **Farbskala Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-343">Right-click the color scale, and then click **Color Scale Properties**.</span></span>  
  
2.  <span data-ttu-id="3fc6d-344">Klicken Sie auf **Number**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-344">Click **Number**.</span></span>  
  
3.  <span data-ttu-id="3fc6d-345">Klicken Sie unter **Kategorie**auf **Währung**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-345">In **Category**, click **Currency**.</span></span>  
  
4.  <span data-ttu-id="3fc6d-346">Geben Sie unter **Dezimalstellen**den Wert **0**ein.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-346">In **Decimal places**, type **0**.</span></span> <span data-ttu-id="3fc6d-347">Dieses Währungsformat enthält keine Dezimalstellen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-347">This format specifies no decimal places for currency.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="3fc6d-348">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-348">Preview the report.</span></span>  
  
 <span data-ttu-id="3fc6d-349">Die Farbskala zeigt für jeden Bereich den Jahresumsatz im Währungsformat an.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-349">The color scale displays annual sales in currency format for each range.</span></span>  
  
###  <a name="6d-create-a-new-legend"></a><a name="NewLegend"></a><span data-ttu-id="3fc6d-350">6d.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-350">6d.</span></span> <span data-ttu-id="3fc6d-351">Erstellen einer neuen Legende</span><span class="sxs-lookup"><span data-stu-id="3fc6d-351">Create a New Legend</span></span>  
 <span data-ttu-id="3fc6d-352">Standardmäßig werden alle Regeln in der ersten Legende angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-352">By default, all rules display in the first legend.</span></span> <span data-ttu-id="3fc6d-353">Sie können Legenden hinzufügen, um die Anzeige für eine Karte zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-353">To improve the display for a map, you can add legends.</span></span>  
  
 <span data-ttu-id="3fc6d-354">Das Ändern der Standardanzeige umfasst zwei Schritte: Erstellen Sie eine neue Legende, und ordnen Sie dann die Regelergebnisse für eine Kartenebene der neuen Legende zu.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-354">To change the default display, there are two steps: create a new legend and then associate the rule results for a map layer with the new legend.</span></span>  
  
##### <a name="to-create-a-new-legend"></a><span data-ttu-id="3fc6d-355">So erstellen Sie eine neue Legende</span><span class="sxs-lookup"><span data-stu-id="3fc6d-355">To create a new legend</span></span>  
  
1.  <span data-ttu-id="3fc6d-356">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-356">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="3fc6d-357">Klicken Sie mit der rechten Maustaste außerhalb des Viewports auf die Karte, und klicken Sie dann auf **Legende hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-357">Right-click the map outside the viewport, and then click **Add Legend**.</span></span> <span data-ttu-id="3fc6d-358">Der Karte wird eine neue Legende an einer Standardposition hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-358">A new legend is added to the map at a default location.</span></span>  
  
3.  <span data-ttu-id="3fc6d-359">Klicken Sie mit der rechten Maustaste auf die Legende, und klicken Sie dann auf **Legenden Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-359">Right-click the legend, and then click **Legend Properties**.</span></span>  
  
4.  <span data-ttu-id="3fc6d-360">Klicken Sie unter **Positions Optionen**auf den Speicherort, der angibt, wo die Legende relativ zum Viewport angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-360">In **Position options**, click the location that specifies where you want the legend to appear relative to the viewport.</span></span> <span data-ttu-id="3fc6d-361">Die Karte auf der Entwurfsoberfläche wird so geändert, dass sie den Effekt der Auswahl anzeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-361">The map on the design surface changes to show the effect of your selections.</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
6.  <span data-ttu-id="3fc6d-362">Klicken Sie auf **Titel** in der Legende, um den Legenden Titel auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-362">Click **Title** on the legend to select the legend title.</span></span>  
  
7.  <span data-ttu-id="3fc6d-363">Klicken Sie erneut auf **Titel** , um den Insert-Modus für den Text einzugeben.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-363">Click **Title** again to enter insert mode for the text.</span></span> <span data-ttu-id="3fc6d-364">Ersetzen Sie **Title** by **Sales (Tausender)**, und klicken Sie dann außerhalb des Texts.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-364">Replace **Title** by **Sales (Thousands)**, and then click outside the text.</span></span>  
  
 <span data-ttu-id="3fc6d-365">Die Legende wird erweitert, um den Titel anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-365">The legend expands to display the title.</span></span>  
  
###  <a name="6e-associate-legend-and-color-rules"></a><a name="Associate"></a><span data-ttu-id="3fc6d-366">6E.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-366">6e.</span></span> <span data-ttu-id="3fc6d-367">Zuordnen der Legende und Farbregeln</span><span class="sxs-lookup"><span data-stu-id="3fc6d-367">Associate Legend and Color Rules</span></span>  
 <span data-ttu-id="3fc6d-368">In jeder Legende können ein oder mehrere Sätze von Regelergebnissen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-368">Each legend can display one or more sets of rule results.</span></span>  
  
##### <a name="to-associate-a-legend-with-color-rules"></a><span data-ttu-id="3fc6d-369">So ordnen Sie einer Legende Farbregeln zu</span><span class="sxs-lookup"><span data-stu-id="3fc6d-369">To associate a legend with color rules</span></span>  
  
1.  <span data-ttu-id="3fc6d-370">Doppelklicken Sie auf die Karte, um den Bereich **Kartenebenen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-370">Double-click the map to display the **Map Layer** pane.</span></span>  
  
2.  <span data-ttu-id="3fc6d-371">Klicken Sie in PolygonLayer1 auf den Pfeil nach unten, und klicken Sie dann auf **Polygon Farbregel**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-371">Click the down arrow on PolygonLayer1, and then click **Polygon Color Rule**.</span></span> <span data-ttu-id="3fc6d-372">Das Dialogfeld **Farbregeleigenschaften der Karte** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-372">The **Map Color Rules Properties** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="3fc6d-373">Klicken Sie auf **Legende**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-373">Click **Legend**.</span></span>  
  
4.  <span data-ttu-id="3fc6d-374">Deaktivieren Sie unter **Farbskalaoptionen die Option** **in Farbskala anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-374">In **Color scale options**, clear **Show in color scale**.</span></span>  
  
5.  <span data-ttu-id="3fc6d-375">Wählen Sie in **Legenden Optionen**in der Dropdown Liste legend2 aus aus.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-375">In **Legend options**, from the drop-down list, select Legend2.</span></span> <span data-ttu-id="3fc6d-376">Die Legendentextoption wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-376">The legend text option appears.</span></span> <span data-ttu-id="3fc6d-377">Standardmäßig wird Legendentext mit einer allgemeinen [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]-Formatzeichenfolge formatiert.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-377">By default, legend text is formatted with a general [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] format string.</span></span> <span data-ttu-id="3fc6d-378">Die 0 in N0 steht für keine Dezimalstellen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-378">The 0 in N0 specifies no decimal digits.</span></span>  
  
6.  <span data-ttu-id="3fc6d-379">Verwenden Sie in **Legenden Text**das folgende Format, um eine Währung ohne Dezimalziffern anzugeben:`#FROMVALUE {C0} - #TOVALUE {C0}`</span><span class="sxs-lookup"><span data-stu-id="3fc6d-379">In **Legend text**, use the following format to specify currency with no decimal digits: `#FROMVALUE {C0} - #TOVALUE {C0}`</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="3fc6d-380">Auf der Entwurfsoberfläche werden die Farbbereiche mit als Währung formatierten Beispieldaten in der Legende angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-380">On the design surface, the legend displays the color ranges with sample data formatted as currency.</span></span>  
  
8.  <span data-ttu-id="3fc6d-381">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-381">Preview the report.</span></span>  
  
 <span data-ttu-id="3fc6d-382">Die Countys mit zugeordneten Geschäften und Umsätzen werden entsprechend den Farbregeln angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-382">The counties that have associated stores and sales display according to the color rules.</span></span> <span data-ttu-id="3fc6d-383">Countys ohne Umsätze ist keine Farbe zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-383">Counties that have no sales have no color.</span></span>  
  
###  <a name="6f-change-color-for-counties-with-no-data"></a><a name="NoData"></a><span data-ttu-id="3fc6d-384">6f.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-384">6f.</span></span> <span data-ttu-id="3fc6d-385">Ändern der Farbe für Countys ohne Daten</span><span class="sxs-lookup"><span data-stu-id="3fc6d-385">Change Color for Counties with No Data</span></span>  
 <span data-ttu-id="3fc6d-386">Sie können die Standardanzeigeoptionen für alle Kartenelemente auf einer Ebene festlegen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-386">You can set the default display options for all map elements on a layer.</span></span> <span data-ttu-id="3fc6d-387">Farbregeln haben Vorrang vor diesen Anzeigeoptionen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-387">Color rules take precedence over these display options.</span></span>  
  
##### <a name="to-set-the-display-properties-for-all-elements-on-a-layer"></a><span data-ttu-id="3fc6d-388">So legen Sie die Anzeigeeigenschaften für alle Elemente auf einer Ebene fest</span><span class="sxs-lookup"><span data-stu-id="3fc6d-388">To set the display properties for all elements on a layer</span></span>  
  
1.  <span data-ttu-id="3fc6d-389">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-389">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="3fc6d-390">Doppelklicken Sie auf die Karte, um den Bereich **Kartenebenen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-390">Double-click the map to display the **Map Layer** pane.</span></span>  
  
3.  <span data-ttu-id="3fc6d-391">Klicken Sie in „PolygonLayer1“ auf den Pfeil nach unten und anschließend auf **Polygoneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-391">Click the down arrow on PolygonLayer1, and then click **Polygon Properties**.</span></span> <span data-ttu-id="3fc6d-392">Das Dialogfeld **Polygoneigenschaften von Karten** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-392">The **Map Polygon Properties** dialog box opens.</span></span> <span data-ttu-id="3fc6d-393">Bevor regelbasierte Anzeigeoptionen angewendet werden, gelten in diesem Dialogfeld festgelegte Anzeigeoptionen für alle Polygone auf der Ebene.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-393">Display options set in this dialog box apply to all polygons on the layer before rule-based display options are applied.</span></span>  
  
4.  <span data-ttu-id="3fc6d-394">Klicken Sie auf **Ausfüllen**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-394">Click **Fill**.</span></span>  
  
5.  <span data-ttu-id="3fc6d-395">Überprüfen Sie, ob der Füllstil vollständig ist **.**</span><span class="sxs-lookup"><span data-stu-id="3fc6d-395">Verify that the fill style is **Solid.**</span></span> <span data-ttu-id="3fc6d-396">festgelegt ist. Farbverläufe und Muster gelten für alle Farben.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-396">Gradients and patterns apply to all colors.</span></span>  
  
6.  <span data-ttu-id="3fc6d-397">Klicken Sie unter **Farbe**auf den Pfeil nach unten, und klicken Sie dann auf **hellstahlblau**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-397">In **Color**, click the down arrow, and then click **Light Steel Blue**.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="3fc6d-398">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-398">Preview the report.</span></span>  
  
 <span data-ttu-id="3fc6d-399">Countys ohne zugeordnete Daten werden blau dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-399">Counties that have no associated data display as blue.</span></span> <span data-ttu-id="3fc6d-400">Nur Countys, denen analytische Daten zugeordnet sind, werden durch **grüne** Farben **aus den von** Ihnen angegebenen Farb Regeln angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-400">Only counties that have associated analytical data appear in the **Red** through **Green** colors from the color rules that you specified.</span></span>  
  
##  <a name="7-add-a-custom-point"></a><a name="CustomPoint"></a><span data-ttu-id="3fc6d-401">7. Hinzufügen eines benutzerdefinierten Punkts</span><span class="sxs-lookup"><span data-stu-id="3fc6d-401">7. Add a Custom Point</span></span>  
 <span data-ttu-id="3fc6d-402">Geben Sie einen Punkt an, und verwenden Sie den Markertyp " **PushPin** ", um einen neuen Speicher darzustellen, der noch nicht erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-402">To represent a new store that has not yet been built, specify a point and use the **PushPin** marker type.</span></span>  
  
#### <a name="to-add-a-custom-point"></a><span data-ttu-id="3fc6d-403">So fügen Sie einen benutzerdefinierten Punkt hinzu</span><span class="sxs-lookup"><span data-stu-id="3fc6d-403">To add a custom point</span></span>  
  
1.  <span data-ttu-id="3fc6d-404">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-404">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="3fc6d-405">Doppelklicken Sie auf die Karte, um den Bereich **Kartenebenen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-405">Double-click the map to display the **Map Layer** pane.</span></span> <span data-ttu-id="3fc6d-406">Klicken Sie auf der Symbolleiste auf **Ebene hinzufügen**, und klicken Sie dann auf **Punkt Ebene**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-406">On the toolbar, click **Add Layer**, and then click **Point Layer**.</span></span>  
  
     <span data-ttu-id="3fc6d-407">Der Karte wird eine neue Punktebene hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-407">A new point layer is added to the map.</span></span> <span data-ttu-id="3fc6d-408">Standardmäßig verfügt die Punktebene über den räumlichen Datentyp **Eingebettet**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-408">By default, the point layer has spatial data type **Embedded**.</span></span>  
  
3.  <span data-ttu-id="3fc6d-409">Klicken Sie in PointLayer2 auf den Pfeil nach unten, und klicken Sie dann auf **Punkt hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-409">Click the down arrow on PointLayer2, and then click **Add Point**.</span></span>  
  
4.  <span data-ttu-id="3fc6d-410">Bewegen Sie den Zeiger über den Kartenviewport.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-410">Move the pointer over the map viewport.</span></span> <span data-ttu-id="3fc6d-411">Der Cursor verändert sich zu einem Fadenkreuz.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-411">The cursor changes to crosshairs.</span></span>  
  
5.  <span data-ttu-id="3fc6d-412">Klicken Sie auf den Ort auf der Karte, an dem Sie einen Punkt hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-412">Click the location on the map where you want to add a point.</span></span> <span data-ttu-id="3fc6d-413">In diesem Lernprogramm klicken Sie auf eine Position in einem County neben dem Start der Route.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-413">In this tutorial, click a location in a county next to the start of the route.</span></span> <span data-ttu-id="3fc6d-414">Der Ebene wird an der Position, an der Sie geklickt haben, ein mit einem Kreis markierter Punkt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-414">A point marked by a circle is added to the layer at the location where you clicked.</span></span> <span data-ttu-id="3fc6d-415">Standardmäßig ist der Punkt ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-415">By default, the point is selected.</span></span>  
  
6.  <span data-ttu-id="3fc6d-416">Klicken Sie mit der rechten Maustaste auf den hinzugefügten Punkt, und klicken Sie anschließend auf **Eigenschaften für eingebettete Punkte**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-416">Right-click the point you added, and then click **Embedded Point Properties**.</span></span>  
  
7.  <span data-ttu-id="3fc6d-417">Wählen Sie die Option **Punkt Optionen für diese Ebene überschreiben aus**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-417">Select the option **Override point options for this layer**.</span></span> <span data-ttu-id="3fc6d-418">Im Dialogfeld werden weitere Seiten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-418">Additional pages appear in the dialog box.</span></span> <span data-ttu-id="3fc6d-419">Hier festgelegte Werte haben Vorrang vor Anzeigeoptionen für die Ebene oder für Farbregeln.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-419">Values that you set here take precedence over display options for the layer or for color rules.</span></span>  
  
8.  <span data-ttu-id="3fc6d-420">Klicken Sie auf **Marker**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-420">Click **Marker**.</span></span>  
  
9. <span data-ttu-id="3fc6d-421">Wählen Sie unter **Markertyp**die Option **Star**aus.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-421">For **Marker type**, select **Star**.</span></span>  
  
10. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
11. <span data-ttu-id="3fc6d-422">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-422">Preview the report.</span></span>  
  
 <span data-ttu-id="3fc6d-423">Der neue Punkt, den Sie hinzugefügt haben, wird als **Stern**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-423">The new point you added appears as a **Star**.</span></span>  
  
#### <a name="to-add-a-label-for-the-custom-point"></a><span data-ttu-id="3fc6d-424">So fügen Sie eine Bezeichnung für den benutzerdefinierten Punkt hinzu</span><span class="sxs-lookup"><span data-stu-id="3fc6d-424">To add a label for the custom point</span></span>  
  
1.  <span data-ttu-id="3fc6d-425">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-425">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="3fc6d-426">Klicken Sie mit der rechten Maustaste auf den soeben hinzugefügten Punkt, und klicken Sie dann auf **Eigenschaften von eingebetteten Punkten**</span><span class="sxs-lookup"><span data-stu-id="3fc6d-426">Right-click the point you just added, and then click **Embedded Point Properties**.</span></span>  
  
3.  <span data-ttu-id="3fc6d-427">Klicken Sie auf **Bezeichnungen**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-427">Click **Labels**.</span></span>  
  
4.  <span data-ttu-id="3fc6d-428">Geben Sie unter Bezeichnungs **Text**den **Wert New Store**ein.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-428">In **Label text**, type **New Store**.</span></span>  
  
5.  <span data-ttu-id="3fc6d-429">Klicken Sie unter **Platzierung**auf **Oben**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-429">In **Placement**, click **Top**.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="3fc6d-430">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-430">Preview the report.</span></span>  
  
 <span data-ttu-id="3fc6d-431">Die Bezeichnung wird über dem Geschäftsstandort angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-431">The label appears above the store location.</span></span>  
  
##  <a name="center-the-map-view"></a><a name="CenterView"></a><span data-ttu-id="3fc6d-432">Zentrieren der Kartenansicht</span><span class="sxs-lookup"><span data-stu-id="3fc6d-432">Center the Map View</span></span>  
 <span data-ttu-id="3fc6d-433">Ändern Sie den Mittelpunkt und die Zoomstufe des Kartenviewports.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-433">Change the map viewport center and zoom level.</span></span>  
  
#### <a name="to-change-the-viewport"></a><span data-ttu-id="3fc6d-434">So ändern Sie den Viewport</span><span class="sxs-lookup"><span data-stu-id="3fc6d-434">To change the viewport</span></span>  
  
1.  <span data-ttu-id="3fc6d-435">Klicken Sie mit der rechten Maustaste auf den Kartenviewport, und klicken Sie dann auf **Viewporteigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-435">Right-click the map viewport, and then click **Viewport Properties**.</span></span>  
  
2.  <span data-ttu-id="3fc6d-436">Klicken Sie auf **zentrieren und Zoomen**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-436">Click **Center and Zoom**.</span></span>  
  
3.  <span data-ttu-id="3fc6d-437">Vergewissern Sie sich, dass die Option **einen Ansichts Mittelpunkt und eine Zoomstufe festlegen** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-437">Verify that the option **Set a view center and zoom level** is selected.</span></span>  
  
4.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="3fc6d-438">Klicken Sie mit der linken Maustaste auf den Kartenviewport, und ziehen Sie den Mittelpunkt des Viewports an die gewünschte Position.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-438">Left-click the map viewport, and drag the center of the viewport to the location that you want.</span></span>  
  
6.  <span data-ttu-id="3fc6d-439">Ändern Sie die Zoomstufe des Viewports mithilfe des Mausrads.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-439">Use the mouse wheel to change the zoom level of the viewport.</span></span>  
  
7.  <span data-ttu-id="3fc6d-440">Zeigen Sie eine Vorschau des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-440">Preview the report.</span></span>  
  
 <span data-ttu-id="3fc6d-441">In der Entwurfsansicht basieren die Karte auf der Anzeigeoberfläche und die Ansicht auf Beispieldaten.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-441">In Design view, the map on the display surface and the view is based on sample data.</span></span> <span data-ttu-id="3fc6d-442">Im gerenderten Bericht wird die Kartenansicht in der angegebenen Ansicht zentriert.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-442">In the rendered report, the map view is centered on the view that you specified.</span></span>  
  
##  <a name="add-a-report-title"></a><a name="Title"></a><span data-ttu-id="3fc6d-443">Hinzufügen eines Berichts Titels</span><span class="sxs-lookup"><span data-stu-id="3fc6d-443">Add a Report Title</span></span>  
  
#### <a name="to-add-a-report-title"></a><span data-ttu-id="3fc6d-444">So fügen Sie einen Berichtstitel hinzu</span><span class="sxs-lookup"><span data-stu-id="3fc6d-444">To add a report title</span></span>  
  
1.  <span data-ttu-id="3fc6d-445">Klicken Sie auf der Entwurfsoberfläche auf **Zum Hinzufügen eines Titels klicken**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-445">On the design surface, click **Click to add title**.</span></span>  
  
2.  <span data-ttu-id="3fc6d-446">Geben Sie **Umsätze in den Geschäften in New York** ein, und klicken Sie anschließend auf den Bereich außerhalb des Textfelds.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-446">Type **Sales in New York Stores** and then click outside the text box.</span></span>  
  
 <span data-ttu-id="3fc6d-447">Dieser Titel wird am Anfang des Berichts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-447">This title will appear at the top of the report.</span></span> <span data-ttu-id="3fc6d-448">Elemente über dem Berichtshauptteil entsprechen einer Berichtskopfzeile, wenn keine Seitenkopfzeile definiert ist.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-448">Items at the top of the report body when there is no page header defined are the equivalent of a report header.</span></span>  
  
##  <a name="save-the-report"></a><a name="Save"></a><span data-ttu-id="3fc6d-449">Speichern des Berichts</span><span class="sxs-lookup"><span data-stu-id="3fc6d-449">Save the Report</span></span>  
  
#### <a name="to-save-the-report"></a><span data-ttu-id="3fc6d-450">So speichern Sie den Bericht</span><span class="sxs-lookup"><span data-stu-id="3fc6d-450">To save the report</span></span>  
  
1.  <span data-ttu-id="3fc6d-451">Wechseln Sie in die Entwurfsansicht.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-451">Switch to Design view.</span></span>  
  
2.  <span data-ttu-id="3fc6d-452">Klicken Sie auf die Schaltfläche Berichts-Generator und anschließend auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-452">From the Report Builder button, click **Save As**.</span></span>  
  
3.  <span data-ttu-id="3fc6d-453">Geben Sie im Feld **Name**den Namen **Umsätze der Geschäfte in New York**ein.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-453">In **Name**, type **Store Sales in New York**.</span></span>  
  
 <span data-ttu-id="3fc6d-454">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-454">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3fc6d-455">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3fc6d-455">Next Steps</span></span>  
 <span data-ttu-id="3fc6d-456">Damit ist die exemplarische Vorgehensweise für das Hinzufügen einer Karte zum Bericht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-456">This concludes the walkthrough for how to add a map to your report.</span></span>  
  
 <span data-ttu-id="3fc6d-457">Weitere Informationen finden Sie unter [Maps &#40;Berichts-Generator und SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) und im Blogeintrag [kartographic-Anpassung räumlicher Daten für SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=152771) auf Blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="3fc6d-457">For more information, see [Maps &#40;Report Builder and SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) and the blog entry [Cartographic Adjustment of Spatial Data for SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=152771) on blogs.msdn.com.</span></span>  
  
 <span data-ttu-id="3fc6d-458">Weitere Tutorials finden Sie unter [Tutorials &#40;Berichts-Generator&#41;](report-builder-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="3fc6d-458">For more tutorials, see [Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fc6d-459">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3fc6d-459">See Also</span></span>  
 <span data-ttu-id="3fc6d-460">[Lernprogramme &#40;Berichts-Generator&#41;](report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="3fc6d-460">[Tutorials &#40;Report Builder&#41;](report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="3fc6d-461">[Berichts-Generator in SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md) </span><span class="sxs-lookup"><span data-stu-id="3fc6d-461">[Report Builder in SQL Server 2014](report-builder/report-builder-in-sql-server-2016.md) </span></span>  
 <span data-ttu-id="3fc6d-462">[Karten-Assistent und Karten Ebenen-Assistent &#40;Berichts-Generator und SSRS&#41;](report-design/map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3fc6d-462">[Map Wizard and Map Layer Wizard &#40;Report Builder and SSRS&#41;](report-design/map-wizard-and-map-layer-wizard-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="3fc6d-463">Unterschiedliche Polygon-, Linien- und Punktanzeigen bei der Verwendung von Regeln und analytischen Daten &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3fc6d-463">Vary Polygon, Line, and Point Display by Rules and Analytical Data &#40;Report Builder and SSRS&#41;</span></span>](report-design/vary-polygon-line-and-point-display-by-rules-and-analytical-data.md)  
  
  
