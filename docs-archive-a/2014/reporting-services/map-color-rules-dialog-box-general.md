---
title: Farb Regeln für Karten (Dialog Feld), allgemein | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10541"
- sql12.rtp.rptdesigner.shared.mapcolorrulesgeneral.f1
ms.assetid: 14ff5fc1-4cf8-4a45-9d98-47a1bf1c52c4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0dffc6c0b31400cb4eb9cecbbada1a52f8f41443
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621867"
---
# <a name="map-color-rules-dialog-box-general"></a><span data-ttu-id="ba388-102">Farbregeln der Karte (Dialogfeld), Allgemein</span><span class="sxs-lookup"><span data-stu-id="ba388-102">Map Color Rules Dialog Box, General</span></span>
  <span data-ttu-id="ba388-103">Wählen Sie **Allgemein** im Dialogfeld für Farbregeleigenschaften \*\*\*\* aus, um Farboptionen für Kartenelemente in dieser Ebene zu definieren.</span><span class="sxs-lookup"><span data-stu-id="ba388-103">Select **General** on the **Color Rules Properties** dialog box to define color options for map elements on this layer.</span></span> <span data-ttu-id="ba388-104">Kartenelemente sind Polygone, Linien und Punkte.</span><span class="sxs-lookup"><span data-stu-id="ba388-104">Map elements include polygons, lines, and points.</span></span> <span data-ttu-id="ba388-105">Farbregeln können angewendet werden, wenn Sie auf der Grundlage räumlicher Daten und analytischer Daten in einem Datasetfeld oder in einem räumlichen Datenquellenfeld eine Beziehung zwischen Kartenelementen erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ba388-105">Color rules can be applied when you have created a relationship between map elements based on spatial data and analytical data from a dataset field or from a spatial data source field.</span></span>  
  
 <span data-ttu-id="ba388-106">Um alle Kartenelemente einer Ebene durch Angeben eines dekorativen Farbverlaufs mit unterschiedlichen primären und sekundären Farben anzuzeigen, verwenden Sie im Dialogfeld Polygoneigenschaften von Karten die Seite **Ausfüllen** .</span><span class="sxs-lookup"><span data-stu-id="ba388-106">To display all map elements on a layer by specifying a decorative gradient with different primary and secondary colors, use the **Fill** page of the Map Polygon Properties Dialog Box.</span></span> <span data-ttu-id="ba388-107">Farbregeln haben Vorrang gegenüber Anzeigeeigenschaften für eine Ebene.</span><span class="sxs-lookup"><span data-stu-id="ba388-107">Color rules take precedence over display properties for a layer.</span></span> <span data-ttu-id="ba388-108">Weitere Informationen finden Sie unter [Anpassen der Daten und der Anzeige einer Karte oder einer Kartenebene &#40;Berichts-Generator und SSRS&#41;](report-design/customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="ba388-108">For more information, see [Customize the Data and Display of a Map or Map Layer &#40;Report Builder and SSRS&#41;](report-design/customize-the-data-and-display-of-a-map-or-map-layer-report-builder-and-ssrs.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ba388-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ba388-109">Options</span></span>  
 <span data-ttu-id="ba388-110">**Vorlagenstil anwenden**</span><span class="sxs-lookup"><span data-stu-id="ba388-110">**Apply template style**</span></span>  
 <span data-ttu-id="ba388-111">Aktivieren Sie diese Option, um Farbe auf Grundlage des Designs zu verwenden, das im Assistenten ausgewählt wurde oder in den Polygon-, Linien- oder Punktebeneneigenschaften festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="ba388-111">Select this option to use color based on the theme that was chosen in the wizard or set in the Polygon, Line, or Point layer properties.</span></span> <span data-ttu-id="ba388-112">Ein Design legt Standardoptionen für Farbe, Schriftart und Rahmen für die Karte fest.</span><span class="sxs-lookup"><span data-stu-id="ba388-112">A theme sets default options for color, font, and borders for the map.</span></span> <span data-ttu-id="ba388-113">Für diese Option wird keine Regel angewendet, um Farben jedem Kartenelement zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="ba388-113">For this option, no rule is applied to assign colors to each map element.</span></span>  
  
 <span data-ttu-id="ba388-114">**Daten mithilfe der Farbpalette anzeigen**</span><span class="sxs-lookup"><span data-stu-id="ba388-114">**Visualize data by using color palette**</span></span>  
 <span data-ttu-id="ba388-115">Aktivieren Sie diese Option, um analytische Daten mithilfe von Farben aus einer bestimmten Farbpalette visuell darzustellen.</span><span class="sxs-lookup"><span data-stu-id="ba388-115">Select this option to visualize analytical data by using colors from a specific color palette.</span></span>  
  
 <span data-ttu-id="ba388-116">**Daten mithilfe von Farbbereichen anzeigen**</span><span class="sxs-lookup"><span data-stu-id="ba388-116">**Visualize data by using color ranges**</span></span>  
 <span data-ttu-id="ba388-117">Aktivieren Sie diese Option, um analytische Daten mit einem Bereich von Farben für jedes Kartenelement visuell darzustellen.</span><span class="sxs-lookup"><span data-stu-id="ba388-117">Select this option to visualize analytical data by using a range of colors for each map element.</span></span> <span data-ttu-id="ba388-118">Wenn Sie z. B. Rot als Startfarbe, Gelb als mittlere Farbe und Grün als Endfarbe angeben, sind Werte im niedrigen Bereich rot, Werte im mittleren Bereich sind gelb, und Werte im obersten Bereich sind grün.</span><span class="sxs-lookup"><span data-stu-id="ba388-118">For example, when you specify Red as a start color, Yellow as a middle color, and Green as an end color, values in the low range are Red, values in the middle range are Yellow, and values in the top range are Green.</span></span>  
  
 <span data-ttu-id="ba388-119">**Daten mithilfe benutzerdefinierter Farben anzeigen**</span><span class="sxs-lookup"><span data-stu-id="ba388-119">**Visualize data by using custom colors**</span></span>  
 <span data-ttu-id="ba388-120">Aktivieren Sie diese Option, um analytische Daten durch das Angeben einer eigenen Liste von Farben visuell darzustellen.</span><span class="sxs-lookup"><span data-stu-id="ba388-120">Select this option to visualize analytical data by specifying your own list of colors.</span></span>  
  
 <span data-ttu-id="ba388-121">**Datenfeld**</span><span class="sxs-lookup"><span data-stu-id="ba388-121">**Data field**</span></span>  
 <span data-ttu-id="ba388-122">Diese Option wird angezeigt, wenn Sie eine der Optionen **Daten anzeigen** auswählen.</span><span class="sxs-lookup"><span data-stu-id="ba388-122">This option appears when you select one of the **Visualize data** options.</span></span>  
  
 <span data-ttu-id="ba388-123">Wählen Sie in der Dropdownliste das zu verwendende Feld mit analytischen Daten aus.</span><span class="sxs-lookup"><span data-stu-id="ba388-123">Select the analytical data field to use from the drop-down list.</span></span> <span data-ttu-id="ba388-124">Abhängig von der Quelle räumlicher Daten zeigt die Liste Felder aus der räumlichen Datenquelle an und aus einem Berichtsdataset, das eine Beziehung zwischen den räumlichen Daten und analytischen Daten darstellt.</span><span class="sxs-lookup"><span data-stu-id="ba388-124">Depending on the source of spatial data, the list displays fields from the spatial data source and from a report dataset that has a relationship between the spatial data and analytical data.</span></span> <span data-ttu-id="ba388-125">Um eine solche Beziehung zu erstellen, legen Sie auf der Seite "Analytische Daten" für die ausgewählte Kartenebene die Datenoptionen fest.</span><span class="sxs-lookup"><span data-stu-id="ba388-125">To create such a relationship, set the data options on the Analytical Data page for the selected map layer.</span></span>  
  
 <span data-ttu-id="ba388-126">**Messer**</span><span class="sxs-lookup"><span data-stu-id="ba388-126">**Palette**</span></span>  
 <span data-ttu-id="ba388-127">Geben Sie den Namen der Farbpalette ein, oder wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="ba388-127">Type or select the name of the color palette.</span></span>  
  
 <span data-ttu-id="ba388-128">**Startfarbe**</span><span class="sxs-lookup"><span data-stu-id="ba388-128">**Start color**</span></span>  
 <span data-ttu-id="ba388-129">Geben Sie die Farbe an, die für Daten am niedrigen Ende des Datenbereichs verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba388-129">Specify the color to use for data at the low end of the data range.</span></span>  
  
 <span data-ttu-id="ba388-130">**Mittelfarbe**</span><span class="sxs-lookup"><span data-stu-id="ba388-130">**Middle color**</span></span>  
 <span data-ttu-id="ba388-131">Geben Sie die Farbe an, die für Daten in der Mitte des Datenbereichs verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba388-131">Specify the color to use for data in the middle of the data range.</span></span> <span data-ttu-id="ba388-132">Wählen Sie **Keine Farbe** aus, um diesen Bereich zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="ba388-132">Select **No Color** to remove this range.</span></span>  
  
 <span data-ttu-id="ba388-133">**Endfarbe**</span><span class="sxs-lookup"><span data-stu-id="ba388-133">**End color**</span></span>  
 <span data-ttu-id="ba388-134">Geben Sie die Farbe an, die für Daten am oberen Ende des Datenbereichs verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba388-134">Specify the color to use for data at the high end of the data range.</span></span>  
  
 <span data-ttu-id="ba388-135">**Add**</span><span class="sxs-lookup"><span data-stu-id="ba388-135">**Add**</span></span>  
 <span data-ttu-id="ba388-136">Klicken Sie auf **Hinzufügen** , um eigene Farben für die Farbregel anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ba388-136">Click **Add** to specify your own colors for the color rule.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba388-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba388-137">See Also</span></span>  
 <span data-ttu-id="ba388-138">[Karten &#40;Berichts-Generator und SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="ba388-138">[Maps &#40;Report Builder and SSRS&#41;](report-design/maps-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="ba388-139">Ändern der Kartenlegenden, Farbskala und zugeordneten Regeln &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="ba388-139">Change Map Legends, Color Scale, and Associated Rules &#40;Report Builder and SSRS&#41;</span></span>](report-design/change-map-legends-color-scale-and-associated-rules-report-builder-and-ssrs.md)  
  
  
