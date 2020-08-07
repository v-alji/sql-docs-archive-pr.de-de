---
title: Eigenschaften des Kartenviewports (Dialog Feld), zentrieren und vergrößern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.mapviewport.centerandzoom.f1
- "10506"
ms.assetid: 642a06f5-293f-48e0-97a6-1489dbefa719
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 913c00773abf71ca627b8cc2a94a873484e8ab30
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615854"
---
# <a name="map-viewport-properties-dialog-box-center-and-zoom"></a><span data-ttu-id="6a68d-102">Eigenschaften des Kartenviewports (Dialogfeld), Zentrieren und zoomen</span><span class="sxs-lookup"><span data-stu-id="6a68d-102">Map Viewport Properties Dialog Box, Center and Zoom</span></span>
  <span data-ttu-id="6a68d-103">Wählen Sie **Zentrieren und zoomen** aus, um im Dialogfeld **Viewporteigenschaften der Karte** die Mittelpunktsicht und den Zoomfaktor für eine Karte festzulegen.</span><span class="sxs-lookup"><span data-stu-id="6a68d-103">Select **Center and Zoom** for the **Map Viewport Properties** dialog box to set the center view and zoom factor for a map.</span></span> <span data-ttu-id="6a68d-104">Nachdem Sie eine Kartendatenquelle und die Begrenzungen der Karte angegeben haben, die Sie in den Bericht einschließen möchten, können Sie den Ansichtmittelpunkt und den Zoomfaktor angeben, um die Kartenanzeige weiter zu steuern.</span><span class="sxs-lookup"><span data-stu-id="6a68d-104">After you specify a map data source and the boundaries of the map that you want to include in your report, you can specify the view center and the zoom factor to further control the map display.</span></span> <span data-ttu-id="6a68d-105">Die Optionen hängen von der Methode ab, die Sie verwenden, um Werte für Mittelpunkt und Zoom anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6a68d-105">Options change depending on which method you use to specify the center and zoom values.</span></span> <span data-ttu-id="6a68d-106">Klicken Sie auf die Schaltfläche **Ausdruck** (*fx*), um einen Ausdruck zu bearbeiten, der den Wert der Option festlegt.</span><span class="sxs-lookup"><span data-stu-id="6a68d-106">Click the **Expression** (*fx*) button to edit an expression that sets the value of the option.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6a68d-107">Optionen</span><span class="sxs-lookup"><span data-stu-id="6a68d-107">Options</span></span>  
 <span data-ttu-id="6a68d-108">**Festlegen eines Ansichtmittelpunktes und einer Zoomstufe**</span><span class="sxs-lookup"><span data-stu-id="6a68d-108">**Set a view center and zoom level**</span></span>  
 <span data-ttu-id="6a68d-109">Wählen Sie diese Option aus, um benutzerdefinierte Werte für den Ansichtmittelpunkt und die Zoomstufe anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6a68d-109">Choose this option to specify custom values for the view center and the zoom level.</span></span>  
  
 <span data-ttu-id="6a68d-110">**Karte zentrieren, um eine Kartenebene anzuzeigen**</span><span class="sxs-lookup"><span data-stu-id="6a68d-110">**Center map to show a map layer**</span></span>  
 <span data-ttu-id="6a68d-111">Wählen Sie diese Option aus, um eine Ebene anzugeben und den Mittelpunkt der Ansicht automatisch auf ihre Kartendaten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="6a68d-111">Choose this option to specify a layer and automatically center the view on its map data.</span></span> <span data-ttu-id="6a68d-112">Legen Sie den Mittelpunkt der Ansicht z. B. auf "LineLayer1" fest.</span><span class="sxs-lookup"><span data-stu-id="6a68d-112">For example, center the view on LineLayer1.</span></span>  
  
 <span data-ttu-id="6a68d-113">**Karte zentrieren, um ein eingebettetes Kartenelement anzuzeigen**</span><span class="sxs-lookup"><span data-stu-id="6a68d-113">**Center map to show an embedded map element**</span></span>  
 <span data-ttu-id="6a68d-114">Wählen Sie diese Option aus, um den Mittelpunkt der Ansicht auf ein bestimmtes datengebundenes Kartenelement festzulegen.</span><span class="sxs-lookup"><span data-stu-id="6a68d-114">Choose this option to center the view on a specific data-bound map element.</span></span> <span data-ttu-id="6a68d-115">Damit diese Option angegeben werden kann, müssen die räumlichen Daten eine Beziehung mit analytischen Daten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6a68d-115">The spatial data must have a relationship with analytical data to specify this option.</span></span>  
  
 <span data-ttu-id="6a68d-116">Legen Sie den Mittelpunkt der Ansicht z. B. auf das Kartenelement fest, für das der Name des Übereinstimmungsfelds [City] und der Übereinstimmungswert "Seattle" lautet.</span><span class="sxs-lookup"><span data-stu-id="6a68d-116">For example, center the view on the map element where the name of the match field is [City] and the match value is "Seattle".</span></span>  
  
 <span data-ttu-id="6a68d-117">**Karte zentrieren, um alle datengebundenen Kartenelemente anzuzeigen**</span><span class="sxs-lookup"><span data-stu-id="6a68d-117">**Center map to show all data-bound map elements**</span></span>  
 <span data-ttu-id="6a68d-118">Wählen Sie diese Option aus, um den Mittelpunkt der Ansicht auf alle Kartenelemente in der Ebene festzulegen.</span><span class="sxs-lookup"><span data-stu-id="6a68d-118">Choose this option to center the view on all map elements in the layer.</span></span> <span data-ttu-id="6a68d-119">Damit diese Option angegeben werden kann, müssen die räumlichen Daten eine Beziehung mit analytischen Daten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6a68d-119">The spatial data must have a relationship with analytical data to specify this option.</span></span>  
  
 <span data-ttu-id="6a68d-120">Legen Sie den Mittelpunkt der Ansicht z. B. auf die Polygonblasenebene fest, auf der Orte angezeigt werden und deren Blasengröße sich auf die Einwohnerzahl bezieht.</span><span class="sxs-lookup"><span data-stu-id="6a68d-120">For example, center the view on the polygon bubble layer that shows cities and the bubble size is related to population.</span></span> <span data-ttu-id="6a68d-121">Beim Berechnen des Mittelpunkts für den Viewport werden nur Orte mit einer entsprechenden Einwohnerzahl eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="6a68d-121">Only those cities with a matching population value are included when calculating the center for the viewport.</span></span>  
  
 <span data-ttu-id="6a68d-122">**Zentrier- und Zoomoptionen**</span><span class="sxs-lookup"><span data-stu-id="6a68d-122">**Center and zoom options**</span></span>  
 <span data-ttu-id="6a68d-123">Wählen Sie eine Option aus, um den Ansichtmittelpunkt und die Zoomstufe anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6a68d-123">Select an option to specify the view center and zoom level.</span></span>  
  
 <span data-ttu-id="6a68d-124">**Mittelpunkt X anzeigen (%)**</span><span class="sxs-lookup"><span data-stu-id="6a68d-124">**View center (X) %**</span></span>  
 <span data-ttu-id="6a68d-125">Die horizontale Koordinate.</span><span class="sxs-lookup"><span data-stu-id="6a68d-125">The horizontal coordinate.</span></span> <span data-ttu-id="6a68d-126">Der Standardwert beträgt 50 %.</span><span class="sxs-lookup"><span data-stu-id="6a68d-126">The default value, 50%.</span></span> <span data-ttu-id="6a68d-127">Er legt fest, dass die Ansicht in der Mitte zwischen dem minimalen und dem maximalen horizontalen Wert zentriert wird.</span><span class="sxs-lookup"><span data-stu-id="6a68d-127">centers the view at the midpoint between the minimum and maximum horizontal values.</span></span>  
  
 <span data-ttu-id="6a68d-128">**Mittelpunkt Y anzeigen (%)**</span><span class="sxs-lookup"><span data-stu-id="6a68d-128">**View center (Y) %**</span></span>  
 <span data-ttu-id="6a68d-129">Die vertikale Koordinate.</span><span class="sxs-lookup"><span data-stu-id="6a68d-129">The vertical coordinate.</span></span> <span data-ttu-id="6a68d-130">Der Standardwert ist 50 %. Er legt fest, dass die Ansicht in der Mitte zwischen dem minimalen und dem maximalen vertikalen Wert zentriert wird.</span><span class="sxs-lookup"><span data-stu-id="6a68d-130">The default value, 50%, centers the view at the midpoint between the minimum and maximum vertical values.</span></span>  
  
 <span data-ttu-id="6a68d-131">**Vergrößerungsstufe (%)**</span><span class="sxs-lookup"><span data-stu-id="6a68d-131">**Zoom level (%)**</span></span>  
 <span data-ttu-id="6a68d-132">Der Zoomfaktor.</span><span class="sxs-lookup"><span data-stu-id="6a68d-132">The zoom factor.</span></span> <span data-ttu-id="6a68d-133">Der Standardwert ist 100 %. Er gibt keine Vergrößerung an.</span><span class="sxs-lookup"><span data-stu-id="6a68d-133">The default value, 100%, indicates no magnification.</span></span>  
  
 <span data-ttu-id="6a68d-134">**Ansicht auf diese Ebene zentrieren**</span><span class="sxs-lookup"><span data-stu-id="6a68d-134">**Center view on this layer**</span></span>  
 <span data-ttu-id="6a68d-135">Gibt den Namen der Ebene an.</span><span class="sxs-lookup"><span data-stu-id="6a68d-135">Specify the name of the layer.</span></span>  
  
 <span data-ttu-id="6a68d-136">**Ansicht auf das Kartenelement zentrieren, das dieser Bedingung entspricht**</span><span class="sxs-lookup"><span data-stu-id="6a68d-136">**Center view on the map element that matches this condition**</span></span>  
 <span data-ttu-id="6a68d-137">Das schreibgeschützte Feld, das angezeigt wird, wird verwendet, um Kartendaten und analytische Daten abzugleichen.</span><span class="sxs-lookup"><span data-stu-id="6a68d-137">The read-only field that is displayed is used to match map data and analytical data.</span></span> <span data-ttu-id="6a68d-138">Geben Sie den Wert an, der für den Abgleich verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6a68d-138">Specify the value that you want to match on.</span></span> <span data-ttu-id="6a68d-139">Die Ansicht wird automatisch auf dieses Kartenelement zentriert.</span><span class="sxs-lookup"><span data-stu-id="6a68d-139">The view automatically centers on this map element.</span></span> <span data-ttu-id="6a68d-140">Beispiel: NAME = TEXAS.</span><span class="sxs-lookup"><span data-stu-id="6a68d-140">For example, NAME = TEXAS.</span></span> <span data-ttu-id="6a68d-141">Standardmäßig ist der Datentyp für die Bedingung "String", und bei der Übereinstimmung wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="6a68d-141">By default, the data type for the condition is String and the match is case-sensitive.</span></span>  
  
 <span data-ttu-id="6a68d-142">Für den Abgleich mit einem Feld, das einen anderen Datentyp aufweist, müssen Sie einen Ausdruck schreiben, der diesen Datentyp ergibt.</span><span class="sxs-lookup"><span data-stu-id="6a68d-142">To match on a field that has a different data type, you must write an expression that evaluates to that data type.</span></span> <span data-ttu-id="6a68d-143">Wenn das Übereinstimmungsfeld z. B. eine fünfstellige Postleitzahl ist, die als ganze Zahl gespeichert wird, müssen Sie zum Angeben der Postleitzahl 98053 den Ausdruck "=98053" verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a68d-143">For example, if the match field is a 5 digit postal code that is stored as an integer, then to specify the postal code 98053, you must use the expression =98053.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a68d-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6a68d-144">See Also</span></span>  
 [<span data-ttu-id="6a68d-145">Karten &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6a68d-145">Maps &#40;Report Builder and SSRS&#41;</span></span>](report-design/maps-report-builder-and-ssrs.md)  
  
  
