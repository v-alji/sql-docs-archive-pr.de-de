---
title: Eigenschaften des Kartenviewports (Dialog Feld), allgemein | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.mapviewport.general.f1
- "10505"
ms.assetid: 6c9c773e-5c56-4571-95ed-8a157cfdfe52
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d760d6a0572cbbd1bd948eab382c0727eb276c4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608384"
---
# <a name="map-viewport-properties-dialog-box-general"></a><span data-ttu-id="f4577-102">Eigenschaften des Kartenviewports (Dialogfeld), Allgemein</span><span class="sxs-lookup"><span data-stu-id="f4577-102">Map Viewport Properties Dialog Box, General</span></span>
  <span data-ttu-id="f4577-103">Wählen Sie im Dialogfeld **Viewporteigenschaften zuordnen** den Bereich **Allgemein** aus, um das Koordinatensystem, die Projektion und die Begrenzungsoptionen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f4577-103">Select **General** on the **Map Viewport Properties** dialog box to change the coordinate system, the projection, and the boundary options.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f4577-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f4577-104">Options</span></span>  
 <span data-ttu-id="f4577-105">**Koordinatensystem**</span><span class="sxs-lookup"><span data-stu-id="f4577-105">**Coordinate system**</span></span>  
 <span data-ttu-id="f4577-106">Geben Sie den Typ des Koordinatensystems an, das für die Kartendaten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f4577-106">Indicate the type of coordinate system that the map data uses.</span></span>  
  
-   <span data-ttu-id="f4577-107">**Planar** Wählen Sie diese Option aus, wenn Kartendaten als x- und y-Koordinaten vorliegen, z. B. zum Erstellen von Plänen.</span><span class="sxs-lookup"><span data-stu-id="f4577-107">**Planar** Choose this option when map data is in X and Y coordinates, for example, for building plans.</span></span>  
  
-   <span data-ttu-id="f4577-108">**Geografisch** Wählen Sie diese Option aus, wenn Kartendaten in Längen- und Breitenkoordinaten vorliegen, z. B. für Orte.</span><span class="sxs-lookup"><span data-stu-id="f4577-108">**Geographic** Choose this option when map data is in longitude and latitude coordinates, for example, for city locations.</span></span>  
  
 <span data-ttu-id="f4577-109">**Projektion**</span><span class="sxs-lookup"><span data-stu-id="f4577-109">**Projection**</span></span>  
 <span data-ttu-id="f4577-110">Geben Sie die Methode an, die verwendet werden soll, um geografische Koordinaten auf eine zweidimensionale Oberfläche zu projizieren.</span><span class="sxs-lookup"><span data-stu-id="f4577-110">Specify the method to use to project geographic coordinates onto a two-dimensional surface.</span></span> <span data-ttu-id="f4577-111">Wählen Sie eine Projektion aus, die mit den visuell darzustellenden Daten kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="f4577-111">Choose a projection that is compatible with the data that you are visualizing.</span></span> <span data-ttu-id="f4577-112">Die vier räumlichen Eigenschaften, die von der Projektion betroffen sind, sind Bereich, Form, Entfernung und Richtung.</span><span class="sxs-lookup"><span data-stu-id="f4577-112">The four spatial properties that are affected by projection are area, shape, distance, and direction.</span></span> <span data-ttu-id="f4577-113">Bei Ansichten der Erde hängt eine gute Auswahl der Projektion von der Mittelpunktansicht, den Kartenbegrenzungen und dem Zoomfaktor ab.</span><span class="sxs-lookup"><span data-stu-id="f4577-113">For views of the earth, a good choice of projection depends on the center view, the map boundaries, and the zoom factor.</span></span>  
  
 <span data-ttu-id="f4577-114">Jede der folgenden Projektionen wahrt mindestens eine der folgenden räumlichen Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f4577-114">Each of the following projections preserves one or more of these spatial properties:</span></span>  
  
-   <span data-ttu-id="f4577-115">**Equirectangular** Wählen Sie diese Option aus, um Längen- und Breitengrad als kartesische Koordinaten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4577-115">**Equirectangular** Choose this option to use longitude and latitude as rectangular coordinates.</span></span>  
  
-   <span data-ttu-id="f4577-116">**Mercator** Wählen Sie diese gängige Projektion für kleinere Bereiche, zum Erzielen von weniger Verzerrung um den Äquator oder wenn Sie eine Kartenebene mit einer vorhandenen Kachelebene hinzufügen möchten, die die Mercator-Projektion verwendet.</span><span class="sxs-lookup"><span data-stu-id="f4577-116">**Mercator** Choose this popular projection for smaller areas, for less distortion around the equator, or when you want to add a map layer with an existing tile layer that uses the Mercator projection.</span></span>  
  
-   <span data-ttu-id="f4577-117">**Robinson** Wählen Sie diese Option, damit große Bereich weniger verzerrt sind, die vom Äquator bis zu den Polen reichen.</span><span class="sxs-lookup"><span data-stu-id="f4577-117">**Robinson** Choose this option for less distortion of large areas that span from the equator to the poles.</span></span> <span data-ttu-id="f4577-118">Diese Projektion wurde von Arthur H. Robinson im Jahr 1963 entwickelt.</span><span class="sxs-lookup"><span data-stu-id="f4577-118">Developed by Arthur H. Robinson in 1963.</span></span>  
  
-   <span data-ttu-id="f4577-119">**Fahey** Wählen Sie diese Option, damit große Bereich weniger verzerrt sind, die vom Äquator bis zu den Polen reichen.</span><span class="sxs-lookup"><span data-stu-id="f4577-119">**Fahey** Choose this option for less distortion of large areas that span from the equator to the poles.</span></span> <span data-ttu-id="f4577-120">Diese Projektion wurde von Lawrence Fahey im Jahr 1975 entwickelt.</span><span class="sxs-lookup"><span data-stu-id="f4577-120">Developed by Lawrence Fahey in 1975.</span></span>  
  
-   <span data-ttu-id="f4577-121">**Eckert1** Wählen Sie diese Option, um äquidistante Parallelen für die Breitengrade und gerade Linien für die Längenmeridiane zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4577-121">**Eckert1** Choose this option to use equally spaced parallels in latitude and straight lines for meridians in longitude.</span></span>  
  
-   <span data-ttu-id="f4577-122">**Eckert3** Wählen Sie diese Option, um äquidistante Parallelen für die Breitengrade und gekrümmte Linien für die Längenmeridiane zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4577-122">**Eckert3** Choose this option to use equally spaced parallels in latitude and curved lines for meridians in longitude.</span></span>  
  
-   <span data-ttu-id="f4577-123">**HammerAitoff** Wählen Sie diese Option für Pol- oder Weltkarten.</span><span class="sxs-lookup"><span data-stu-id="f4577-123">**HammerAitoff** Choose this option for polar maps or world maps.</span></span>  
  
-   <span data-ttu-id="f4577-124">**Wagner3** Wählen Sie diese Option für Weltkarten.</span><span class="sxs-lookup"><span data-stu-id="f4577-124">**Wagner3** Choose this option for world maps.</span></span>  
  
-   <span data-ttu-id="f4577-125">**Bonne** Wählen Sie diese Option, um die Welt wie in einem Atlas anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f4577-125">**Bonne** Choose this option to view the world as it appears in an atlas.</span></span>  
  
 <span data-ttu-id="f4577-126">**Seitenumbruchoptionen**</span><span class="sxs-lookup"><span data-stu-id="f4577-126">**Page break options**</span></span>  
 <span data-ttu-id="f4577-127">Wählen Sie Optionen aus, um anzugeben, wie der Inhalt an eine Berichtsseite angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="f4577-127">Select options to indicate how content is fitted to a report page.</span></span>  
  
 <span data-ttu-id="f4577-128">**Begrenzungsoptionen**</span><span class="sxs-lookup"><span data-stu-id="f4577-128">**Boundary options**</span></span>  
 <span data-ttu-id="f4577-129">Geben Sie die Unter- und die Obergrenzen für Koordinaten an, um zu steuern, welcher Teil der Karte im Bericht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f4577-129">Specify the lower and upper boundaries for coordinates to control which part of the map appears in the report.</span></span>  
  
 <span data-ttu-id="f4577-130">**Minimum (X)**</span><span class="sxs-lookup"><span data-stu-id="f4577-130">**Minimum X**</span></span>  
 <span data-ttu-id="f4577-131">Niedrigster X-Wert.</span><span class="sxs-lookup"><span data-stu-id="f4577-131">Lowest X value.</span></span> <span data-ttu-id="f4577-132">Nur für **Planar** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f4577-132">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="f4577-133">**Maximum (X)**</span><span class="sxs-lookup"><span data-stu-id="f4577-133">**Maximum X**</span></span>  
 <span data-ttu-id="f4577-134">Höchster X-Wert.</span><span class="sxs-lookup"><span data-stu-id="f4577-134">Highest X value.</span></span> <span data-ttu-id="f4577-135">Nur für **Planar** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f4577-135">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="f4577-136">**Minimum (Y)**</span><span class="sxs-lookup"><span data-stu-id="f4577-136">**Minimum Y**</span></span>  
 <span data-ttu-id="f4577-137">Niedrigster Y-Wert.</span><span class="sxs-lookup"><span data-stu-id="f4577-137">Lowest Y value.</span></span> <span data-ttu-id="f4577-138">Nur für **Planar** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f4577-138">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="f4577-139">**Maximum (Y)**</span><span class="sxs-lookup"><span data-stu-id="f4577-139">**Maximum Y**</span></span>  
 <span data-ttu-id="f4577-140">Höchster Y-Wert.</span><span class="sxs-lookup"><span data-stu-id="f4577-140">Highest Y value.</span></span> <span data-ttu-id="f4577-141">Nur für **Planar** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f4577-141">Available for **Planar** only.</span></span>  
  
 <span data-ttu-id="f4577-142">**Minimale Länge**</span><span class="sxs-lookup"><span data-stu-id="f4577-142">**Minimum Longitude**</span></span>  
 <span data-ttu-id="f4577-143">Niedrigster Längenwert.</span><span class="sxs-lookup"><span data-stu-id="f4577-143">Lowest longitude value.</span></span> <span data-ttu-id="f4577-144">Nur für **Geografisch** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f4577-144">Available for **Geographic** only.</span></span>  
  
 <span data-ttu-id="f4577-145">**Maximale Länge**</span><span class="sxs-lookup"><span data-stu-id="f4577-145">**Maximum Longitude**</span></span>  
 <span data-ttu-id="f4577-146">Höchster Längenwert.</span><span class="sxs-lookup"><span data-stu-id="f4577-146">Highest longitude value.</span></span> <span data-ttu-id="f4577-147">Nur für **Geografisch** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f4577-147">Available for **Geographic** only.</span></span>  
  
 <span data-ttu-id="f4577-148">**Minimale Breite**</span><span class="sxs-lookup"><span data-stu-id="f4577-148">**Minimum Latitude**</span></span>  
 <span data-ttu-id="f4577-149">Niedrigster Breitenwert.</span><span class="sxs-lookup"><span data-stu-id="f4577-149">Lowest latitude value.</span></span> <span data-ttu-id="f4577-150">Nur für **Geografisch** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f4577-150">Available for **Geographic** only.</span></span>  
  
 <span data-ttu-id="f4577-151">**Maximale Breite**</span><span class="sxs-lookup"><span data-stu-id="f4577-151">**Maximum Latitude**</span></span>  
 <span data-ttu-id="f4577-152">Höchster Breitenwert.</span><span class="sxs-lookup"><span data-stu-id="f4577-152">Highest latitude value.</span></span> <span data-ttu-id="f4577-153">Nur für **Geografisch** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f4577-153">Available for **Geographic** only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4577-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f4577-154">See Also</span></span>  
 [<span data-ttu-id="f4577-155">Karten &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="f4577-155">Maps &#40;Report Builder and SSRS&#41;</span></span>](report-design/maps-report-builder-and-ssrs.md)  
  
  
