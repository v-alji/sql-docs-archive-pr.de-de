---
title: Erstellen, Aufbauen und Abfragen von geometry-Instanzen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- planar spatial data [SQL Server], getting started
- geometry data type [SQL Server], getting started
ms.assetid: c6b5c852-37d2-48d0-a8ad-e43bb80d6514
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 539f3f8bb1d9a1c277d6317cc571cf8bcb281833
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609059"
---
# <a name="create-construct-and-query-geometry-instances"></a><span data-ttu-id="01d2e-102">Erstellen, Aufbauen und Abfragen von geometry-Instanzen</span><span class="sxs-lookup"><span data-stu-id="01d2e-102">Create, Construct, and Query geometry Instances</span></span>
  <span data-ttu-id="01d2e-103">Der planare räumliche Datentyp `geometry` stellt Daten in einem euklidischen (flachen) Koordinatensystem dar.</span><span class="sxs-lookup"><span data-stu-id="01d2e-103">The planar spatial data type, `geometry`, represents data in a Euclidean (flat) coordinate system.</span></span> <span data-ttu-id="01d2e-104">Dieser Datentyp wird in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]als CLR-Datentyp (Common Language Runtime) implementiert.</span><span class="sxs-lookup"><span data-stu-id="01d2e-104">This type is implemented as a common language runtime (CLR) data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="01d2e-105">Der `geometry`-Typ ist vordefiniert und in jeder Datenbank verfügbar.</span><span class="sxs-lookup"><span data-stu-id="01d2e-105">The `geometry` type is predefined and available in each database.</span></span> <span data-ttu-id="01d2e-106">Sie können Tabellenspalten des `geometry`-Typs in der gleichen Weise erstellen und `geometry`-Daten in der gleichen Weise verwenden wie andere CLR-Typen.</span><span class="sxs-lookup"><span data-stu-id="01d2e-106">You can create table columns of type `geometry` and operate on `geometry` data in the same manner as you would use other CLR types.</span></span>  
  
 <span data-ttu-id="01d2e-107">Der (planare) `geometry`-Datentyp, der von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützt wird, entspricht der Open Geospatial Consortium (OGC) Simple Features for SQL Specification Version 1.1.0.</span><span class="sxs-lookup"><span data-stu-id="01d2e-107">The `geometry` data type (planar) supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conforms to the Open Geospatial Consortium (OGC) Simple Features for SQL Specification version 1.1.0.</span></span>  
  
 <span data-ttu-id="01d2e-108">Weitere Informationen zu den OGC-Spezifikationen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="01d2e-108">For more information on OGC specifications, see the following:</span></span>  
  
-   [<span data-ttu-id="01d2e-109">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span><span class="sxs-lookup"><span data-stu-id="01d2e-109">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span></span>](https://go.microsoft.com/fwlink/?LinkId=93628)  
  
-   [<span data-ttu-id="01d2e-110">OGC Specifications, Simple Feature Access Part 2: SQL Options (OGC-Spezifikationen, Simple Feature Access, Teil 2: SQL-Optionen)</span><span class="sxs-lookup"><span data-stu-id="01d2e-110">OGC Specifications, Simple Feature Access Part 2 - SQL Options</span></span>](https://go.microsoft.com/fwlink/?LinkId=93629)  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="01d2e-111">unterstützt eine Teilmenge des vorhandenen GML 3.1-Standards, der in folgendem Schema definiert ist: [https://schemas.microsoft.com/sqlserver/profiles/gml/SpatialGML.xsd](https://go.microsoft.com/fwlink/?LinkId=230959).</span><span class="sxs-lookup"><span data-stu-id="01d2e-111">supports a subset of the existing GML 3.1 standard which is defined in the following schema: [https://schemas.microsoft.com/sqlserver/profiles/gml/SpatialGML.xsd](https://go.microsoft.com/fwlink/?LinkId=230959).</span></span>  
  
##  <a name="creating-or-constructing-a-new-geometry-instance"></a><a name="creating"></a> <span data-ttu-id="01d2e-112">Erstellen oder Konstruieren einer neuen geometry-Instanz</span><span class="sxs-lookup"><span data-stu-id="01d2e-112">Creating or constructing a new geometry instance</span></span>  
  
###  <a name="creating-a-new-geometry-instance-from-an-existing-instance"></a><a name="existing"></a> <span data-ttu-id="01d2e-113">Erstellen einer neuen geometry-Instanz aus einer vorhandenen Instanz</span><span class="sxs-lookup"><span data-stu-id="01d2e-113">Creating a New geometry Instance from an Existing Instance</span></span>  
 <span data-ttu-id="01d2e-114">Der `geometry`-Datentyp stellt viele integrierte Methoden zur Verfügung, mit denen neue `geometry`-Instanzen auf der Grundlage vorhandener Instanzen erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="01d2e-114">The `geometry` data type provides numerous built-in methods you can use to create new `geometry` instances based on existing instances.</span></span>  
  
 <span data-ttu-id="01d2e-115">**So erstellen Sie einen Puffer um eine Geometrie**</span><span class="sxs-lookup"><span data-stu-id="01d2e-115">**To create a buffer around a geometry**</span></span>  
 [<span data-ttu-id="01d2e-116">STBuffer &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-116">STBuffer &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stbuffer-geometry-data-type)  
  
 [<span data-ttu-id="01d2e-117">BufferWithTolerance &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-117">BufferWithTolerance &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/bufferwithtolerance-geometry-data-type)  
  
 <span data-ttu-id="01d2e-118">**So erstellen Sie eine vereinfachte Version einer Geometrie**</span><span class="sxs-lookup"><span data-stu-id="01d2e-118">**To create a simplified version of a geometry**</span></span>  
 [<span data-ttu-id="01d2e-119">Reduce &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-119">Reduce &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/reduce-geometry-data-type)  
  
 <span data-ttu-id="01d2e-120">**So erstellen Sie die konvexe Hülle einer Geometrie**</span><span class="sxs-lookup"><span data-stu-id="01d2e-120">**To create the convex hull of a geometry**</span></span>  
 [<span data-ttu-id="01d2e-121">STConvexHull &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-121">STConvexHull &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stconvexhull-geometry-data-type)  
  
 <span data-ttu-id="01d2e-122">**So erstellen Sie eine Geometrie aus der Schnittmenge zweier Geometrien**</span><span class="sxs-lookup"><span data-stu-id="01d2e-122">**To create a geometry from the intersection of two geometries**</span></span>  
 [<span data-ttu-id="01d2e-123">STIntersection &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-123">STIntersection &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stintersection-geometry-data-type)  
  
 <span data-ttu-id="01d2e-124">**So erstellen Sie eine Geometrie aus der Vereinigung zweier Geometrien**</span><span class="sxs-lookup"><span data-stu-id="01d2e-124">**To create a geometry from the union of two geometries**</span></span>  
 [<span data-ttu-id="01d2e-125">STUnion &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-125">STUnion &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stunion-geometry-data-type)  
  
 <span data-ttu-id="01d2e-126">**So erstellen Sie eine Geometrie aus den Punkten, an denen eine Geometrie eine andere nicht überlappt**</span><span class="sxs-lookup"><span data-stu-id="01d2e-126">**To create a geometry from the points where one geometry does not overlap another**</span></span>  
 [<span data-ttu-id="01d2e-127">STDifference &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-127">STDifference &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stdifference-geometry-data-type)  
  
 <span data-ttu-id="01d2e-128">**So erstellen Sie eine Geometrie aus den Punkten, an denen zwei Geometrien nicht überlappen**</span><span class="sxs-lookup"><span data-stu-id="01d2e-128">**To create a geometry from the points where two geometries do not overlap**</span></span>  
 [<span data-ttu-id="01d2e-129">STSymDifference &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-129">STSymDifference &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stsymdifference-geometry-data-type)  
  
 <span data-ttu-id="01d2e-130">**So erstellen Sie eine beliebige Punktinstanz, die auf einer vorhandenen Geometrie liegt**</span><span class="sxs-lookup"><span data-stu-id="01d2e-130">**To create an arbitrary Point instance that lies on an existing geometry**</span></span>  
 [<span data-ttu-id="01d2e-131">STPointOnSurface &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-131">STPointOnSurface &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type)  
  
  
  
###  <a name="constructing-a-geometry-instance-from-well-known-text-input"></a><a name="wkt"></a> <span data-ttu-id="01d2e-132">Erstellen einer geometry-Instanz anhand einer WKT-Eingabe (Well-Known Text)</span><span class="sxs-lookup"><span data-stu-id="01d2e-132">Constructing a geometry Instance from Well-Known Text Input</span></span>  
 <span data-ttu-id="01d2e-133">Der `geometry`-Datentyp bietet mehrere integrierte Methoden zur Erstellung einer Geometrie anhand der WKT-Darstellung von Open Geospatial Consortium (OGC).</span><span class="sxs-lookup"><span data-stu-id="01d2e-133">The `geometry` data type provides several built-in methods that generate a geometry from the Open Geospatial Consortium (OGC) WKT representation.</span></span> <span data-ttu-id="01d2e-134">Der WKT-Standard ist eine Textzeichenfolge, die den Austausch von Geometriedaten in Textform ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="01d2e-134">The WKT standard is a text string that allows geometry data to be exchanged in textual form.</span></span>  
  
 <span data-ttu-id="01d2e-135">**So erstellen Sie eine beliebige geometry-Instanz anhand einer WKT-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="01d2e-135">**To construct any type of geometry instance from WKT input**</span></span>  
 [<span data-ttu-id="01d2e-136">STGeomFromText &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-136">STGeomFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomfromtext-geometry-data-type)  
  
 [<span data-ttu-id="01d2e-137">Parse &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-137">Parse &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/parse-geometry-data-type)  
  
 <span data-ttu-id="01d2e-138">**So erstellen Sie eine Point-geometry-Instanz anhand einer WKT-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="01d2e-138">**To construct a geometry Point instance from WKT input**</span></span>  
 [<span data-ttu-id="01d2e-139">STPointFromText &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-139">STPointFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointfromtext-geometry-data-type)  
  
 <span data-ttu-id="01d2e-140">**So erstellen Sie eine MultiPoint-geometry-Instanz anhand einer WKT-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="01d2e-140">**To construct a geometry MultiPoint instance from WKT input**</span></span>  
 [<span data-ttu-id="01d2e-141">STMPointFromText &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-141">STMPointFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpointfromtext-geometry-data-type)  
  
 <span data-ttu-id="01d2e-142">**So erstellen Sie eine LineString-geometry-Instanz anhand einer WKT-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="01d2e-142">**To construct a geometry LineString instance from WKT input**</span></span>  
 [<span data-ttu-id="01d2e-143">STLineFromText &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-143">STLineFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stlinefromtext-geometry-data-type)  
  
 <span data-ttu-id="01d2e-144">**So erstellen Sie eine MultiLineString-geometry-Instanz anhand einer WKT-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="01d2e-144">**To construct a geometry MultiLineString instance from WKT input**</span></span>  
 [<span data-ttu-id="01d2e-145">STMLineFromText &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-145">STMLineFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmlinefromtext-geometry-data-type)  
  
 <span data-ttu-id="01d2e-146">**So erstellen Sie eine Polygon-geometry-Instanz anhand einer WKT-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="01d2e-146">**To construct a geometry Polygon instance from WKT input**</span></span>  
 [<span data-ttu-id="01d2e-147">STPolyFromText &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-147">STPolyFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpolyfromtext-geometry-data-type)  
  
 <span data-ttu-id="01d2e-148">**So erstellen Sie eine MultiPolygon-geometry-Instanz anhand einer WKT-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="01d2e-148">**To construct a geometry MultiPolygon instance from WKT input**</span></span>  
 [<span data-ttu-id="01d2e-149">STMPolyFromText &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-149">STMPolyFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpolyfromtext-geometry-data-type)  
  
 <span data-ttu-id="01d2e-150">**So erstellen Sie eine GeometryCollection-geometry-Instanz anhand einer WKT-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="01d2e-150">**To construct a geometry GeometryCollection instance from WKT input**</span></span>  
 [<span data-ttu-id="01d2e-151">STGeomCollFromText &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-151">STGeomCollFromText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomcollfromtext-geometry-data-type)  
  
  
  
###  <a name="constructing-a-geometry-instance-from-well-known-binary-input"></a><a name="wkb"></a> <span data-ttu-id="01d2e-152">Erstellen einer geometry-Instanz aus einer WKB-Eingabe (Well-Known Binary)</span><span class="sxs-lookup"><span data-stu-id="01d2e-152">Constructing a geometry Instance from Well-Known Binary Input</span></span>  
 <span data-ttu-id="01d2e-153">WKB ist ein vom Open Geospatial Consortium spezifiziertes Binärformat, das den Austausch von `geometry`-Daten zwischen einer Clientanwendung und einer SQL-Datenbank ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="01d2e-153">WKB is a binary format specified by the Open Geospatial Consortium (OGC) that permits `geometry` data to be exchanged between a client application and an SQL database.</span></span> <span data-ttu-id="01d2e-154">Die folgenden Funktionen akzeptieren die WKB-Eingabe zum Zweck der Erstellung von Geometrien:</span><span class="sxs-lookup"><span data-stu-id="01d2e-154">The following functions accept WKB input to construct geometries:</span></span>  
  
 <span data-ttu-id="01d2e-155">**So erstellen Sie einen beliebigen geometry-Instanztyp anhand einer WKB-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="01d2e-155">**To construct any type of geometry instance from WKB input**</span></span>  
 [<span data-ttu-id="01d2e-156">STGeomFromWKB &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-156">STGeomFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomfromwkb-geometry-data-type)  
  
 <span data-ttu-id="01d2e-157">**So erstellen Sie eine Point-geometry-Instanz anhand einer WKB-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="01d2e-157">**To construct a geometry Point instance from WKB input**</span></span>  
 [<span data-ttu-id="01d2e-158">STPointFromWKB &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-158">STPointFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointfromwkb-geometry-data-type)  
  
 <span data-ttu-id="01d2e-159">**So erstellen Sie eine MultiPoint-geometry-Instanz anhand einer WKB-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="01d2e-159">**To construct a geometry MultiPoint instance from WKB input**</span></span>  
 [<span data-ttu-id="01d2e-160">STMPointFromWKB &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-160">STMPointFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpointfromwkb-geometry-data-type)  
  
 <span data-ttu-id="01d2e-161">**So erstellen Sie eine LineString-geometry-Instanz anhand einer WKB-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="01d2e-161">**To construct a geometry LineString instance from WKB input**</span></span>  
 [<span data-ttu-id="01d2e-162">STLineFromWKB &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-162">STLineFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stlinefromwkb-geometry-data-type)  
  
 <span data-ttu-id="01d2e-163">**So erstellen Sie eine MultiLineString-geometry-Instanz anhand einer WKB-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="01d2e-163">**To construct a geometry MultiLineString instance from WKB input**</span></span>  
 [<span data-ttu-id="01d2e-164">STMLineFromWKB &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-164">STMLineFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmlinefromwkb-geometry-data-type)  
  
 <span data-ttu-id="01d2e-165">**So erstellen Sie eine Polygon-geometry-Instanz anhand einer WKB-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="01d2e-165">**To construct a geometry Polygon instance from WKB input**</span></span>  
 [<span data-ttu-id="01d2e-166">STPolyFromWKB &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-166">STPolyFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpolyfromwkb-geometry-data-type)  
  
 <span data-ttu-id="01d2e-167">**So erstellen Sie eine MultiPolygon-geometry-Instanz anhand einer WKB-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="01d2e-167">**To construct a geometry MultiPolygon instance from WKB input**</span></span>  
 [<span data-ttu-id="01d2e-168">STMPolyFromWKB &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-168">STMPolyFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stmpolyfromwkb-geometry-data-type)  
  
 <span data-ttu-id="01d2e-169">**So erstellen Sie eine GeometryCollection-geometry-Instanz anhand einer WKB-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="01d2e-169">**To construct a geometry GeometryCollection instance from WKB input**</span></span>  
 [<span data-ttu-id="01d2e-170">STGeomCollFromWKB &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-170">STGeomCollFromWKB &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeomcollfromwkb-geometry-data-type)  
  
  
  
###  <a name="constructing-a-geometry-instance-from-gml-text-input"></a><a name="gml"></a> <span data-ttu-id="01d2e-171">Erstellen einer geometry-Instanz anhand einer GML-Texteingabe</span><span class="sxs-lookup"><span data-stu-id="01d2e-171">Constructing a geometry Instance from GML Text Input</span></span>  
 <span data-ttu-id="01d2e-172">Der- `geometry` Datentyp stellt eine Methode bereit, die eine- `geometry` Instanz aus GML generiert, einer XML-Darstellung geometrischer Objekte.</span><span class="sxs-lookup"><span data-stu-id="01d2e-172">The `geometry` data type provides a method that generates a `geometry` instance from GML, an XML representation of geometric objects.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="01d2e-173">unterstützt eine Teilmenge von GML.</span><span class="sxs-lookup"><span data-stu-id="01d2e-173">supports a subset of GML.</span></span>  
  
 <span data-ttu-id="01d2e-174">**So erstellen Sie einen beliebigen geometry-Instanztyp anhand einer GML-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="01d2e-174">**To construct any type of geometry instance from GML input**</span></span>  
 [<span data-ttu-id="01d2e-175">GeomFromGml &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-175">GeomFromGml &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/geomfromgml-geometry-data-type)  
  
  
  
##  <a name="returning-well-known-text-and-well-known-binary-from-a-geometry-instance"></a><a name="returning"></a> <span data-ttu-id="01d2e-176">Zurückgeben von WKT (Well-Known Text) oder WKB (Well-Known Binary) aus einer geometry-Instanz</span><span class="sxs-lookup"><span data-stu-id="01d2e-176">Returning Well-Known Text and Well-Known Binary from a geometry Instance</span></span>  
 <span data-ttu-id="01d2e-177">Anhand der folgenden Methoden können Sie entweder das WKT- oder das WKB-Format einer `geometry` zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="01d2e-177">You can use the following methods to return either the WKT or WKB format of a `geometry` instance:</span></span>  
  
 <span data-ttu-id="01d2e-178">**So geben Sie eine WKT-Darstellung einer geometry-Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-178">**To return the WKT representation of a geometry instance**</span></span>  
 [<span data-ttu-id="01d2e-179">STAsText &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-179">STAsText &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stastext-geometry-data-type)  
  
 [<span data-ttu-id="01d2e-180">ToString &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-180">ToString &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/tostring-geometry-data-type)  
  
 <span data-ttu-id="01d2e-181">**So geben Sie eine WKT-Darstellung einer geometry-Instanz einschließlich Z- und M-Werten zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-181">**To return the WKT representation of a geometry instance including any Z and M values**</span></span>  
 [<span data-ttu-id="01d2e-182">AsTextZM &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-182">AsTextZM &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/astextzm-geometry-data-type)  
  
 <span data-ttu-id="01d2e-183">**So geben Sie eine WKB-Darstellung einer geometry-Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-183">**To return the WKB representation of a geometry instance**</span></span>  
 [<span data-ttu-id="01d2e-184">STAsBinary &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-184">STAsBinary &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stasbinary-geometry-data-type)  
  
 <span data-ttu-id="01d2e-185">**So geben Sie eine GML-Darstellung einer geometry-Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-185">**To return a GML representation of a geometry instance**</span></span>  
 [<span data-ttu-id="01d2e-186">AsGml &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-186">AsGml &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/asgml-geometry-data-type)  
  
  
  
##  <a name="querying-the-properties-and-behaviors-of-geometry-instances"></a><a name="querying"></a> <span data-ttu-id="01d2e-187">Abfragen der Eigenschaften und Verhalten von geometry-Instanzen</span><span class="sxs-lookup"><span data-stu-id="01d2e-187">Querying the Properties and Behaviors of geometry Instances</span></span>  
 <span data-ttu-id="01d2e-188">Alle- `geometry` Instanzen verfügen über eine Reihe von Eigenschaften, die über von bereitgestellte Methoden abgerufen werden können [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="01d2e-188">All `geometry` instances have a number of properties that can be retrieved through methods that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides.</span></span> <span data-ttu-id="01d2e-189">In den folgenden Themen werden die Eigenschaften und Verhalten von geometry-Typen und die Methoden zum Abrufen der einzelnen Eigenschaften und Verhalten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="01d2e-189">The following topics define the properties and behaviors of geometry types, and the methods for querying each one.</span></span>  
  
###  <a name="validity-instance-type-and-geometrycollection-information"></a><a name="valid"></a> <span data-ttu-id="01d2e-190">Gültigkeit, Instanztyp und GeometryCollection-Informationen</span><span class="sxs-lookup"><span data-stu-id="01d2e-190">Validity, Instance Type, and GeometryCollection Information</span></span>  
 <span data-ttu-id="01d2e-191">Sobald eine `geometry`-Instanz erstellt wurde, können Sie anhand der folgenden Methoden ermitteln, ob sie wohlgeformt ist, den Instanztyp zurückgeben oder, wenn es sich um eine Collection-Instanz handelt, eine spezifische `geometry`-Instanz zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="01d2e-191">Once a `geometry` instance is constructed, you can use the following methods to determine if it is well-formed, return the instance type, or, if it is a collection instance, return a specific `geometry` instance.</span></span>  
  
 <span data-ttu-id="01d2e-192">**So geben Sie den Instanztyp einer Geometrie zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-192">**To return the instance type of a geometry**</span></span>  
 [<span data-ttu-id="01d2e-193">STGeometryType &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-193">STGeometryType &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stgeometrytype-geometry-data-type)  
  
 <span data-ttu-id="01d2e-194">**So bestimmen Sie, ob eine Geometrie einen gegebenen Instanztyp aufweist**</span><span class="sxs-lookup"><span data-stu-id="01d2e-194">**To determine if a geometry is a given instance type**</span></span>  
 [<span data-ttu-id="01d2e-195">InstanceOf &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-195">InstanceOf &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/instanceof-geometry-data-type)  
  
 <span data-ttu-id="01d2e-196">**So bestimmen Sie, ob eine geometry-Instanz für ihren Instanztyp wohlgeformt ist**</span><span class="sxs-lookup"><span data-stu-id="01d2e-196">**To determine if a geometry instance is well-formed for its instance type**</span></span>  
 [<span data-ttu-id="01d2e-197">STIsValid &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-197">STIsValid &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type)  
  
 <span data-ttu-id="01d2e-198">**So konvertieren Sie eine geometry-Instanz in eine wohlgeformte Geometrieinstanz mit einem Instanztyp**</span><span class="sxs-lookup"><span data-stu-id="01d2e-198">**To convert a geometry instance to a well-formed geometry instance with an instance type**</span></span>  
 [<span data-ttu-id="01d2e-199">MakeValid &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-199">MakeValid &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/makevalid-geometry-data-type)  
  
 <span data-ttu-id="01d2e-200">**So geben Sie die Anzahl von Geometrien in einer geometry-Auflistungsinstanz zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-200">**To return the number of geometries in a geometry collection instance**</span></span>  
 [<span data-ttu-id="01d2e-201">STNumGeometries &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-201">STNumGeometries &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stnumgeometries-geometry-data-type)  
  
 <span data-ttu-id="01d2e-202">So geben Sie eine bestimmte Geometrie in einer geometry-Auflistungsinstanz zurück</span><span class="sxs-lookup"><span data-stu-id="01d2e-202">To return a specific geometry in a geometry collection instance</span></span>  
 <span data-ttu-id="01d2e-203">[STGeometryN &#40;geometry-Datentyp&#41;](/sql/t-sql/spatial-geometry/stgeometryn-geometry-data-type)STGeometryN (geometry-Datentyp)</span><span class="sxs-lookup"><span data-stu-id="01d2e-203">[STGeometryN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stgeometryn-geometry-data-type)STGeometryN (geometry Data type)</span></span>  
  
  
  
###  <a name="number-of-points"></a><a name="number"></a> <span data-ttu-id="01d2e-204">Anzahl von Punkten</span><span class="sxs-lookup"><span data-stu-id="01d2e-204">Number of Points</span></span>  
 <span data-ttu-id="01d2e-205">Alle nicht leeren `geometry` Instanzen bestehen aus *Punkten*.</span><span class="sxs-lookup"><span data-stu-id="01d2e-205">All nonempty `geometry` instances are comprised of *points*.</span></span> <span data-ttu-id="01d2e-206">Diese Punkte stellen die x- und y-Koordinaten der Ebene dar, auf die die Geometrien gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="01d2e-206">These points represent the X- and Y-coordinates of the plane on which the geometries are drawn.</span></span> <span data-ttu-id="01d2e-207">`geometry` stellt zahlreiche integrierte Methoden zum Abfragen der Punkte einer Instanz bereit.</span><span class="sxs-lookup"><span data-stu-id="01d2e-207">`geometry` provides numerous built-in methods for querying the points of an instance.</span></span>  
  
 <span data-ttu-id="01d2e-208">**So geben Sie die Anzahl von Punkten zurück, aus denen eine Instanz besteht**</span><span class="sxs-lookup"><span data-stu-id="01d2e-208">**To return the number of points that comprise an instance**</span></span>  
 [<span data-ttu-id="01d2e-209">STNumPoints &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-209">STNumPoints &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type)  
  
 <span data-ttu-id="01d2e-210">**So geben Sie einen bestimmten Punkt einer Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-210">**To return a specific point in an instance**</span></span>  
 [<span data-ttu-id="01d2e-211">STPointN</span><span class="sxs-lookup"><span data-stu-id="01d2e-211">STPointN</span></span>](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type)  
  
 <span data-ttu-id="01d2e-212">**So geben Sie einen beliebigen Punkt zurück, der auf einer Instanz liegt**</span><span class="sxs-lookup"><span data-stu-id="01d2e-212">**To return an arbitrary point that lies on an instance**</span></span>  
 [<span data-ttu-id="01d2e-213">STPointOnSurface</span><span class="sxs-lookup"><span data-stu-id="01d2e-213">STPointOnSurface</span></span>](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type)  
  
 <span data-ttu-id="01d2e-214">**So geben Sie den Ausgangspunkt einer Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-214">**To return the start point of an instance**</span></span>  
 [<span data-ttu-id="01d2e-215">STStartPoint</span><span class="sxs-lookup"><span data-stu-id="01d2e-215">STStartPoint</span></span>](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type)  
  
 <span data-ttu-id="01d2e-216">**So geben Sie den Endpunkt einer Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-216">**To return the end point of an instance**</span></span>  
 [<span data-ttu-id="01d2e-217">STEndpoint</span><span class="sxs-lookup"><span data-stu-id="01d2e-217">STEndpoint</span></span>](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type)  
  
 <span data-ttu-id="01d2e-218">**So geben Sie die X-Koordinate einer Point-Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-218">**To return the X-coordinate of a Point instance**</span></span>  
 [<span data-ttu-id="01d2e-219">STX &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-219">STX &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stx-geometry-data-type)  
  
 <span data-ttu-id="01d2e-220">**So geben Sie die Y-Koordinate einer Point-Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-220">**To return the Y-coordinate of a Point instance**</span></span>  
 [<span data-ttu-id="01d2e-221">STY</span><span class="sxs-lookup"><span data-stu-id="01d2e-221">STY</span></span>](/sql/t-sql/spatial-geometry/sty-geometry-data-type)  
  
 <span data-ttu-id="01d2e-222">**So geben Sie den geometrischen Mittelpunkt einer Polygon-, CurvePolygon- oder MultiPolygon-Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-222">**To return the geometric center point of a Polygon, CurvePolygon, or MultiPolygon instance**</span></span>  
 [<span data-ttu-id="01d2e-223">STCentroid</span><span class="sxs-lookup"><span data-stu-id="01d2e-223">STCentroid</span></span>](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type)  
  
  
  
###  <a name="dimension"></a><a name="dimension"></a> <span data-ttu-id="01d2e-224">Dimension</span><span class="sxs-lookup"><span data-stu-id="01d2e-224">Dimension</span></span>  
 <span data-ttu-id="01d2e-225">Eine nicht leere `geometry`-Instanz kann null-, ein- oder zweidimensional sein.</span><span class="sxs-lookup"><span data-stu-id="01d2e-225">A nonempty `geometry` instance can be 0-, 1-, or 2-dimensional.</span></span> <span data-ttu-id="01d2e-226">Nulldimensionale Objekte (`geometries`), z. B. `Point` und `MultiPoint`, verfügen weder über eine Länge noch über eine Fläche.</span><span class="sxs-lookup"><span data-stu-id="01d2e-226">Zero-dimensional `geometries`, such as `Point` and `MultiPoint`, have no length or area.</span></span> <span data-ttu-id="01d2e-227">Eindimensionale Objekte (z. B. `LineString, CircularString, CompoundCurve` und `MultiLineString`) weisen eine Länge auf.</span><span class="sxs-lookup"><span data-stu-id="01d2e-227">One-dimensional objects, such as `LineString, CircularString, CompoundCurve`, and `MultiLineString`, have length.</span></span> <span data-ttu-id="01d2e-228">Zweidimensionale Instanzen (z. B. `Polygon`, `CurvePolygon` und `MultiPolygon`) weisen eine Fläche und eine Länge auf.</span><span class="sxs-lookup"><span data-stu-id="01d2e-228">Two-dimensional instances, such as `Polygon`, `CurvePolygon`, and `MultiPolygon`, have area and length.</span></span> <span data-ttu-id="01d2e-229">Für leere Instanzen wird als Dimension -1 ausgegeben, und für eine `GeometryCollection`-Auflistung wird eine Fläche ausgegeben, die vom Typ der darin enthaltenen Elemente abhängt.</span><span class="sxs-lookup"><span data-stu-id="01d2e-229">Empty instances will report a dimension of -1, and a `GeometryCollection` will report an area dependent on the types of its contents.</span></span>  
  
 <span data-ttu-id="01d2e-230">**So geben Sie die Dimension einer Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-230">**To return the dimension of an instance**</span></span>  
 [<span data-ttu-id="01d2e-231">STDimension</span><span class="sxs-lookup"><span data-stu-id="01d2e-231">STDimension</span></span>](/sql/t-sql/spatial-geometry/stdimension-geometry-data-type)  
  
 <span data-ttu-id="01d2e-232">**So geben Sie die Länge einer Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-232">**To return the length of an instance**</span></span>  
 [<span data-ttu-id="01d2e-233">STLength</span><span class="sxs-lookup"><span data-stu-id="01d2e-233">STLength</span></span>](/sql/t-sql/spatial-geometry/stlength-geometry-data-type)  
  
 <span data-ttu-id="01d2e-234">**So geben Sie die Fläche einer Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-234">**To return the area of an instance**</span></span>  
 [<span data-ttu-id="01d2e-235">STArea</span><span class="sxs-lookup"><span data-stu-id="01d2e-235">STArea</span></span>](/sql/t-sql/spatial-geometry/starea-geometry-data-type)  
  
  
  
###  <a name="empty"></a><a name="empty"></a> <span data-ttu-id="01d2e-236">Empty</span><span class="sxs-lookup"><span data-stu-id="01d2e-236">Empty</span></span>  
 <span data-ttu-id="01d2e-237">Eine *leere* - `geometry` Instanz besitzt keine Punkte.</span><span class="sxs-lookup"><span data-stu-id="01d2e-237">An *empty*`geometry` instance does not have any points.</span></span> <span data-ttu-id="01d2e-238">Die Länge von leeren `LineString, CircularString` `CompoundCurve` -,-und- `MultiLineString` Instanzen ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="01d2e-238">The length of empty `LineString, CircularString`, `CompoundCurve`, and `MultiLineString` instances is zero.</span></span> <span data-ttu-id="01d2e-239">Die Fläche von leeren `Polygon`-, `CurvePolygon`- und `MultiPolygon`-Instanzen ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="01d2e-239">The area of empty `Polygon`, `CurvePolygon`, and `MultiPolygon` instances is 0.</span></span>  
  
 <span data-ttu-id="01d2e-240">**So bestimmen Sie, ob eine Instanz leer ist**</span><span class="sxs-lookup"><span data-stu-id="01d2e-240">**To determine if an instance is empty**</span></span>  
 <span data-ttu-id="01d2e-241">[STIsEmpty](/sql/t-sql/spatial-geometry/stisempty-geometry-data-type).</span><span class="sxs-lookup"><span data-stu-id="01d2e-241">[STIsEmpty](/sql/t-sql/spatial-geometry/stisempty-geometry-data-type).</span></span>  
  
  
  
###  <a name="simple"></a><a name="simple"></a> <span data-ttu-id="01d2e-242">Einfach</span><span class="sxs-lookup"><span data-stu-id="01d2e-242">Simple</span></span>  
 <span data-ttu-id="01d2e-243">Damit eine `geometry` der-Instanz *einfach*ist, muss Sie beide Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="01d2e-243">For a `geometry` of the instance to be *simple*, it must meet both of these requirements:</span></span>  
  
-   <span data-ttu-id="01d2e-244">Keine Abbildung der Instanz darf sich selbst außer an den Endpunkten schneiden.</span><span class="sxs-lookup"><span data-stu-id="01d2e-244">Each figure of the instance must not intersect itself, except at its endpoints.</span></span>  
  
-   <span data-ttu-id="01d2e-245">Keine zwei Abbildungen einer Instanz dürfen sich an einem Punkt schneiden, der nicht auf den Umrisslinien dieser beiden Abbildungen liegt.</span><span class="sxs-lookup"><span data-stu-id="01d2e-245">No two figures of the instance can intersect each other at a point that is not in both of their boundaries.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="01d2e-246">Leere Geometrien sind stets einfach.</span><span class="sxs-lookup"><span data-stu-id="01d2e-246">Empty geometries are always simple.</span></span>  
  
 <span data-ttu-id="01d2e-247">**So bestimmen Sie, ob eine Instanz einfach ist**</span><span class="sxs-lookup"><span data-stu-id="01d2e-247">**To determine if an instance is simple**</span></span>  
 <span data-ttu-id="01d2e-248">[STIsSimple](/sql/t-sql/spatial-geometry/stissimple-geometry-data-type).</span><span class="sxs-lookup"><span data-stu-id="01d2e-248">[STIsSimple](/sql/t-sql/spatial-geometry/stissimple-geometry-data-type).</span></span>  
  
  
  
###  <a name="boundary-interior-and-exterior"></a><a name="boundary"></a> <span data-ttu-id="01d2e-249">Begrenzung, Innenbereich und Außenbereich</span><span class="sxs-lookup"><span data-stu-id="01d2e-249">Boundary, Interior, and Exterior</span></span>  
 <span data-ttu-id="01d2e-250">Das *innere* einer- `geometry` Instanz ist der von der-Instanz belegte Speicherplatz, und der *äußere* Bereich ist der Platz, der nicht belegt ist.</span><span class="sxs-lookup"><span data-stu-id="01d2e-250">The *interior* of a `geometry` instance is the space occupied by the instance, and the *exterior* is the space not occupied it.</span></span>  
  
 <span data-ttu-id="01d2e-251">Die*Begrenzung* wird vom OGC wie folgt definiert:</span><span class="sxs-lookup"><span data-stu-id="01d2e-251">*Boundary* is defined by the OGC as follows:</span></span>  
  
-   <span data-ttu-id="01d2e-252">`Point`- und `MultiPoint`-Instanzen haben keine Begrenzung.</span><span class="sxs-lookup"><span data-stu-id="01d2e-252">`Point` and `MultiPoint` instances do not have a boundary.</span></span>  
  
-   <span data-ttu-id="01d2e-253">Die Begrenzung von `LineString`- und `MultiLineString`-Instanzen werden durch die Anfangs- und Endpunkte gebildet, wobei die Punkte entfernt werden, die eine gerade Anzahl von Malen vorkommen.</span><span class="sxs-lookup"><span data-stu-id="01d2e-253">`LineString` and `MultiLineString` boundaries are formed by the start points and end points, removing those that occur an even number of times.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 1, 0 0, 1 0, 0 1), (1 1, 1 0))');  
SELECT @g.STBoundary().ToString();  
```  
  
 <span data-ttu-id="01d2e-254">Die Begrenzung einer `Polygon`- oder `MultiPolygon`-Instanz besteht aus der Menge ihrer Ringe.</span><span class="sxs-lookup"><span data-stu-id="01d2e-254">The boundary of a `Polygon` or `MultiPolygon` instance is the set of its rings.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('POLYGON((0 0, 3 0, 3 3, 0 3, 0 0), (1 1, 1 2, 2 2, 2 1, 1 1))');  
SELECT @g.STBoundary().ToString();  
```  
  
 <span data-ttu-id="01d2e-255">**So geben Sie die Begrenzung einer Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-255">**To return the boundary of an instance**</span></span>  
 [<span data-ttu-id="01d2e-256">STBoundary</span><span class="sxs-lookup"><span data-stu-id="01d2e-256">STBoundary</span></span>](/sql/t-sql/spatial-geometry/stboundary-geometry-data-type)  
  
  
  
###  <a name="envelope"></a><a name="envelope"></a> <span data-ttu-id="01d2e-257">Umschlag</span><span class="sxs-lookup"><span data-stu-id="01d2e-257">Envelope</span></span>  
 <span data-ttu-id="01d2e-258">Der *Umschlag* einer `geometry` -Instanz, die auch als *Begrenzungs*Rahmen bezeichnet wird, ist das Achsen ausgerichtete Rechteck, das durch die minimalen und maximalen (X, Y) Koordinaten der-Instanz gebildet wird.</span><span class="sxs-lookup"><span data-stu-id="01d2e-258">The *envelope* of a `geometry` instance, also known as the *bounding box*, is the axis-aligned rectangle formed by the minimum and maximum (X,Y) coordinates of the instance.</span></span>  
  
 <span data-ttu-id="01d2e-259">**So geben Sie den Umschlag einer Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-259">**To return the envelope of an instance**</span></span>  
 [<span data-ttu-id="01d2e-260">STEnvelope</span><span class="sxs-lookup"><span data-stu-id="01d2e-260">STEnvelope</span></span>](/sql/t-sql/spatial-geometry/stenvelope-geometry-data-type)  
  
  
  
###  <a name="closure"></a><a name="closure"></a> <span data-ttu-id="01d2e-261">Abgeschlossenheit</span><span class="sxs-lookup"><span data-stu-id="01d2e-261">Closure</span></span>  
 <span data-ttu-id="01d2e-262">Eine *geschlossene* - `geometry` Instanz ist eine Abbildung, deren Start-und Endpunkte identisch sind.</span><span class="sxs-lookup"><span data-stu-id="01d2e-262">A *closed*`geometry` instance is a figure whose start points and end points are the same.</span></span> <span data-ttu-id="01d2e-263">Alle `Polygon`-Instanzen gelten als geschlossen.</span><span class="sxs-lookup"><span data-stu-id="01d2e-263">`Polygon` instances are considered closed.</span></span> <span data-ttu-id="01d2e-264">Alle `Point`-Instanzen gelten als nicht geschlossen.</span><span class="sxs-lookup"><span data-stu-id="01d2e-264">`Point` instances are not closed.</span></span>  
  
 <span data-ttu-id="01d2e-265">Ein Ring ist eine einfache, geschlossene `LineString`-Instanz.</span><span class="sxs-lookup"><span data-stu-id="01d2e-265">A ring is a simple, closed `LineString` instance.</span></span>  
  
 <span data-ttu-id="01d2e-266">**So bestimmen Sie, ob eine Instanz abgeschlossen ist**</span><span class="sxs-lookup"><span data-stu-id="01d2e-266">**To determine if an instance is closed**</span></span>  
 [<span data-ttu-id="01d2e-267">STIsClosed</span><span class="sxs-lookup"><span data-stu-id="01d2e-267">STIsClosed</span></span>](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type)  
  
 <span data-ttu-id="01d2e-268">**So bestimmen Sie, ob eine Instanz ein Ring ist**</span><span class="sxs-lookup"><span data-stu-id="01d2e-268">**To determine if an instance is a ring**</span></span>  
 [<span data-ttu-id="01d2e-269">STIsRing</span><span class="sxs-lookup"><span data-stu-id="01d2e-269">STIsRing</span></span>](/sql/t-sql/spatial-geometry/stisring-geometry-data-type)  
  
 <span data-ttu-id="01d2e-270">**So geben Sie den äußeren Ring einer Polygoninstanz zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-270">**To return the exterior ring of a Polygon instance**</span></span>  
 [<span data-ttu-id="01d2e-271">STExteriorRing</span><span class="sxs-lookup"><span data-stu-id="01d2e-271">STExteriorRing</span></span>](/sql/t-sql/spatial-geometry/stexteriorring-geometry-data-type)  
  
 <span data-ttu-id="01d2e-272">**So geben Sie die Anzahl der inneren Ringen in einer Polygoninstanz zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-272">**To return the number of interior rings in a Polygon**</span></span>  
 [<span data-ttu-id="01d2e-273">STNumInteriorRing</span><span class="sxs-lookup"><span data-stu-id="01d2e-273">STNumInteriorRing</span></span>](/sql/t-sql/spatial-geometry/stnuminteriorring-geometry-data-type)  
  
 <span data-ttu-id="01d2e-274">**So geben Sie einen gegebenen inneren Ring einer Polygoninstanz zurück**</span><span class="sxs-lookup"><span data-stu-id="01d2e-274">**To return a specified interior ring of a Polygon**</span></span>  
 [<span data-ttu-id="01d2e-275">STInteriorRingN</span><span class="sxs-lookup"><span data-stu-id="01d2e-275">STInteriorRingN</span></span>](/sql/t-sql/spatial-geometry/stinteriorringn-geometry-data-type)  
  
  
  
###  <a name="spatial-reference-id-srid"></a><a name="srid"></a> <span data-ttu-id="01d2e-276">SRID (Spatial Reference ID)</span><span class="sxs-lookup"><span data-stu-id="01d2e-276">Spatial Reference ID (SRID)</span></span>  
 <span data-ttu-id="01d2e-277">Der SRID (Spatial Reference ID) ist ein Bezeichner, der das Koordinatensystem angibt, in dem die `geometry`-Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="01d2e-277">The spatial reference ID (SRID) is an identifier specifying which coordinate system the `geometry` instance is represented in.</span></span> <span data-ttu-id="01d2e-278">Zwei Instanzen mit unterschiedlichen SRIDs können nicht verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="01d2e-278">Two instances with different SRIDs are incomparable.</span></span>  
  
 <span data-ttu-id="01d2e-279">**So können Sie die SRID einer Instanz festlegen oder zurückgeben**</span><span class="sxs-lookup"><span data-stu-id="01d2e-279">**To set or return the SRID of an instance**</span></span>  
 [<span data-ttu-id="01d2e-280">STSrid</span><span class="sxs-lookup"><span data-stu-id="01d2e-280">STSrid</span></span>](/sql/t-sql/spatial-geometry/stsrid-geometry-data-type)  
  
 <span data-ttu-id="01d2e-281">Diese Eigenschaft kann geändert werden.</span><span class="sxs-lookup"><span data-stu-id="01d2e-281">This property can be modified.</span></span>  
  
  
  
##  <a name="determining-relationships-between-geometry-instances"></a><a name="rel"></a> <span data-ttu-id="01d2e-282">Bestimmen der Beziehungen zwischen geometry-Instanzen</span><span class="sxs-lookup"><span data-stu-id="01d2e-282">Determining Relationships between geometry Instances</span></span>  
 <span data-ttu-id="01d2e-283">Der `geometry`-Datentyp stellt viele integrierte Methoden zur Verfügung, mit denen die Beziehungen zwischen zwei `geometry`-Instanzen bestimmt werden können.</span><span class="sxs-lookup"><span data-stu-id="01d2e-283">The `geometry` data type provides many built-in methods you can use to determine relationships between two `geometry` instances.</span></span>  
  
 <span data-ttu-id="01d2e-284">**So bestimmen Sie, ob zwei Instanzen die gleiche Punktmenge umfassen**</span><span class="sxs-lookup"><span data-stu-id="01d2e-284">**To determine if two instances comprise the same point set**</span></span>  
 [<span data-ttu-id="01d2e-285">STEquals</span><span class="sxs-lookup"><span data-stu-id="01d2e-285">STEquals</span></span>](/sql/t-sql/spatial-geometry/stequals-geometry-data-type)  
  
 <span data-ttu-id="01d2e-286">**So bestimmen Sie, ob zwei Instanzen disjunkt sind**</span><span class="sxs-lookup"><span data-stu-id="01d2e-286">**To determine if two instances are disjoint**</span></span>  
 [<span data-ttu-id="01d2e-287">STDisjoint</span><span class="sxs-lookup"><span data-stu-id="01d2e-287">STDisjoint</span></span>](/sql/t-sql/spatial-geometry/stdisjoint-geometry-data-type)  
  
 <span data-ttu-id="01d2e-288">**So bestimmen Sie, ob sich zwei Instanzen überschneiden**</span><span class="sxs-lookup"><span data-stu-id="01d2e-288">**To determine if two instances intersect**</span></span>  
 [<span data-ttu-id="01d2e-289">STIntersects</span><span class="sxs-lookup"><span data-stu-id="01d2e-289">STIntersects</span></span>](/sql/t-sql/spatial-geometry/stintersects-geometry-data-type)  
  
 <span data-ttu-id="01d2e-290">**So bestimmen Sie, ob sich zwei Instanzen berühren**</span><span class="sxs-lookup"><span data-stu-id="01d2e-290">**To determine if two instances touch**</span></span>  
 [<span data-ttu-id="01d2e-291">STTouches</span><span class="sxs-lookup"><span data-stu-id="01d2e-291">STTouches</span></span>](/sql/t-sql/spatial-geometry/sttouches-geometry-data-type)  
  
 <span data-ttu-id="01d2e-292">**So bestimmen Sie, ob sich zwei Instanzen überlappen**</span><span class="sxs-lookup"><span data-stu-id="01d2e-292">**To determine if two instances overlap**</span></span>  
 [<span data-ttu-id="01d2e-293">STOverlaps</span><span class="sxs-lookup"><span data-stu-id="01d2e-293">STOverlaps</span></span>](/sql/t-sql/spatial-geometry/stoverlaps-geometry-data-type)  
  
 <span data-ttu-id="01d2e-294">**So bestimmen Sie, ob sich zwei Instanzen überkreuzen**</span><span class="sxs-lookup"><span data-stu-id="01d2e-294">**To determine if two instances cross**</span></span>  
 [<span data-ttu-id="01d2e-295">STCrosses</span><span class="sxs-lookup"><span data-stu-id="01d2e-295">STCrosses</span></span>](/sql/t-sql/spatial-geometry/stcrosses-geometry-data-type)  
  
 <span data-ttu-id="01d2e-296">**So bestimmen Sie, ob eine Instanz sich innerhalb einer anderen befindet**</span><span class="sxs-lookup"><span data-stu-id="01d2e-296">**To determine if one instance is within another**</span></span>  
 [<span data-ttu-id="01d2e-297">STWithin</span><span class="sxs-lookup"><span data-stu-id="01d2e-297">STWithin</span></span>](/sql/t-sql/spatial-geometry/stwithin-geometry-data-type)  
  
 <span data-ttu-id="01d2e-298">**So bestimmen Sie, ob eine Instanz eine andere enthält**</span><span class="sxs-lookup"><span data-stu-id="01d2e-298">**To determine if one instance contains another**</span></span>  
 [<span data-ttu-id="01d2e-299">STContains</span><span class="sxs-lookup"><span data-stu-id="01d2e-299">STContains</span></span>](/sql/t-sql/spatial-geometry/stcontains-geometry-data-type)  
  
 <span data-ttu-id="01d2e-300">**So bestimmen Sie, ob eine Instanz eine andere überlappt**</span><span class="sxs-lookup"><span data-stu-id="01d2e-300">**To determine if one instance overlaps another**</span></span>  
 [<span data-ttu-id="01d2e-301">STOverlaps</span><span class="sxs-lookup"><span data-stu-id="01d2e-301">STOverlaps</span></span>](/sql/t-sql/spatial-geometry/stoverlaps-geometry-data-type)  
  
 <span data-ttu-id="01d2e-302">**So bestimmen Sie, ob zwei Instanzen räumlich verbunden sind**</span><span class="sxs-lookup"><span data-stu-id="01d2e-302">**To determine if two instances are spatially related**</span></span>  
 [<span data-ttu-id="01d2e-303">STRelate</span><span class="sxs-lookup"><span data-stu-id="01d2e-303">STRelate</span></span>](/sql/t-sql/spatial-geometry/strelate-geometry-data-type)  
  
 <span data-ttu-id="01d2e-304">**So bestimmen Sie die kürzeste Entfernung zwischen Punkten in zwei Geometrien**</span><span class="sxs-lookup"><span data-stu-id="01d2e-304">**To determine the shortest distance between points in two geometries**</span></span>  
 [<span data-ttu-id="01d2e-305">STDistance</span><span class="sxs-lookup"><span data-stu-id="01d2e-305">STDistance</span></span>](/sql/t-sql/spatial-geometry/stdistance-geometry-data-type)  
  
  
  
##  <a name="geometry-instances-default-to-zero-srid"></a><a name="defaultsrid"></a> <span data-ttu-id="01d2e-306">geometry-Instanzen haben standardmäßig die SRID 0 (null)</span><span class="sxs-lookup"><span data-stu-id="01d2e-306">geometry Instances Default to Zero SRID</span></span>  
 <span data-ttu-id="01d2e-307">Der Standard-SRID für `geometry`-Instanzen lautet in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 0.</span><span class="sxs-lookup"><span data-stu-id="01d2e-307">The default SRID for `geometry` instances in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is 0.</span></span> <span data-ttu-id="01d2e-308">Bei räumlichen `geometry`-Daten ist zur Ausführung von Berechnungen des SRID der Räumlichkeitsinstanz nicht erforderlich. Daher können sich Instanzen in einer undefinierten ebenen Fläche befinden.</span><span class="sxs-lookup"><span data-stu-id="01d2e-308">With `geometry` spatial data, the specific SRID of the spatial instance is not required to perform calculations; thus, instances can reside in undefined planar space.</span></span> <span data-ttu-id="01d2e-309">Zur Angabe einer undefinierten ebenen Fläche in Berechnungen mit Methoden des `geometry`-Datentyps wird in [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] der SRID 0 verwendet.</span><span class="sxs-lookup"><span data-stu-id="01d2e-309">To indicate undefined planar space in the calculations of `geometry` data type methods, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses SRID 0.</span></span>  
  
##  <a name="examples"></a><a name="examples"></a> <span data-ttu-id="01d2e-310">Beispiele</span><span class="sxs-lookup"><span data-stu-id="01d2e-310">Examples</span></span>  
 <span data-ttu-id="01d2e-311">Die folgenden zwei Beispiele zeigen, wie Geometriedaten hinzugefügt und abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="01d2e-311">The following two examples show how to add and query geometry data.</span></span>  
  
-   <span data-ttu-id="01d2e-312">Im ersten Beispiel wird eine Tabelle mit einer Identitätsspalte und der `geometry` -Spalte `GeomCol1`erstellt.</span><span class="sxs-lookup"><span data-stu-id="01d2e-312">The first example creates a table with an identity column and a `geometry` column `GeomCol1`.</span></span> <span data-ttu-id="01d2e-313">Eine dritte Spalte rendert die `geometry` -Spalte als Darstellung im Open Geospatial Consortium (OGC) WKT-Format und verwendet die `STAsText()` -Methode.</span><span class="sxs-lookup"><span data-stu-id="01d2e-313">A third column renders the `geometry` column into its Open Geospatial Consortium (OGC) Well-Known Text (WKT) representation, and uses the `STAsText()` method.</span></span> <span data-ttu-id="01d2e-314">Dann werden zwei Zeilen eingefügt: Eine Zeile enthält eine `LineString` -Instanz des Typs `geometry`und die andere eine `Polygon` -Instanz.</span><span class="sxs-lookup"><span data-stu-id="01d2e-314">Two rows are then inserted: one row contains a `LineString` instance of `geometry`, and one row contains a `Polygon` instance.</span></span>  
  
    ```  
    IF OBJECT_ID ( 'dbo.SpatialTable', 'U' ) IS NOT NULL   
        DROP TABLE dbo.SpatialTable;  
    GO  
  
    CREATE TABLE SpatialTable   
        ( id int IDENTITY (1,1),  
        GeomCol1 geometry,   
        GeomCol2 AS GeomCol1.STAsText() );  
    GO  
  
    INSERT INTO SpatialTable (GeomCol1)  
    VALUES (geometry::STGeomFromText('LINESTRING (100 100, 20 180, 180 180)', 0));  
  
    INSERT INTO SpatialTable (GeomCol1)  
    VALUES (geometry::STGeomFromText('POLYGON ((0 0, 150 0, 150 150, 0 150, 0 0))', 0));  
    GO  
    ```  
  
-   <span data-ttu-id="01d2e-315">Im zweiten Beispiel werden mithilfe der `STIntersection()` -Methode die Punkte zurückgegeben, an denen die beiden zuvor eingegebenen `geometry` -Instanzen sich schneiden.</span><span class="sxs-lookup"><span data-stu-id="01d2e-315">The second example uses the `STIntersection()` method to return the points where the two previously inserted `geometry` instances intersect.</span></span>  
  
    ```  
    DECLARE @geom1 geometry;  
    DECLARE @geom2 geometry;  
    DECLARE @result geometry;  
  
    SELECT @geom1 = GeomCol1 FROM SpatialTable WHERE id = 1;  
    SELECT @geom2 = GeomCol1 FROM SpatialTable WHERE id = 2;  
    SELECT @result = @geom1.STIntersection(@geom2);  
    SELECT @result.STAsText();  
    ```  
  
  
  
## <a name="see-also"></a><span data-ttu-id="01d2e-316">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="01d2e-316">See Also</span></span>  
 [<span data-ttu-id="01d2e-317">Räumliche Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="01d2e-317">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
