---
title: Erstellen, Aufbauen und Abfragen von geography-Instanzen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geography data type [SQL Server]
- geodetic data type [SQL Server]
- geography data type [SQL Server], about geography data type
ms.assetid: b585851e-d15b-411f-adeb-aeabeb777c0b
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: d744457cc517a6172cca96b27eae1f456deca24e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609061"
---
# <a name="create-construct-and-query-geography-instances"></a><span data-ttu-id="95bfe-102">Erstellen, Aufbauen und Abfragen von geography-Instanzen</span><span class="sxs-lookup"><span data-stu-id="95bfe-102">Create, Construct, and Query geography Instances</span></span>
  <span data-ttu-id="95bfe-103">Der räumliche `geography`-Datentyp stellt Daten in einem Erdkugel-Koordinatensystem dar.</span><span class="sxs-lookup"><span data-stu-id="95bfe-103">The geography spatial data type, `geography`, represents data in a round-earth coordinate system.</span></span> <span data-ttu-id="95bfe-104">Dieser Datentyp wird in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]als .NET CLR-Datentyp (Common Language Runtime) implementiert.</span><span class="sxs-lookup"><span data-stu-id="95bfe-104">This type is implemented as a .NET common language runtime (CLR) data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="95bfe-105">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `geography` -Datentyp speichert ellipsenförmige Daten (Round-Earth), z. b. GPS-breiten-und Längenkoordinaten.</span><span class="sxs-lookup"><span data-stu-id="95bfe-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `geography` data type stores ellipsoidal (round-earth) data, such as GPS latitude and longitude coordinates.</span></span>  
  
 <span data-ttu-id="95bfe-106">Der `geography`-Typ ist vordefiniert und in jeder Datenbank verfügbar.</span><span class="sxs-lookup"><span data-stu-id="95bfe-106">The `geography` type is predefined and available in each database.</span></span> <span data-ttu-id="95bfe-107">Sie können Tabellenspalten des `geography`-Typs in der gleichen Weise erstellen und `geography`-Daten in der gleichen Weise verwenden wie andere vom System bereitgestellte Typen.</span><span class="sxs-lookup"><span data-stu-id="95bfe-107">You can create table columns of type `geography` and operate on `geography` data in the same manner as you would use other system-supplied types.</span></span>  
  
##  <a name="creating-or-constructing-a-new-geography-instance"></a><a name="creating"></a> <span data-ttu-id="95bfe-108">Erstellen einer neuen geography-Instanz</span><span class="sxs-lookup"><span data-stu-id="95bfe-108">Creating or constructing a new geography instance</span></span>  
  
###  <a name="creating-a-new-geography-instance-from-an-existing-instance"></a><a name="existing"></a> <span data-ttu-id="95bfe-109">Erstellen einer neuen geography-Instanz anhand einer vorhandenen Instanz</span><span class="sxs-lookup"><span data-stu-id="95bfe-109">Creating a New geography Instance from an Existing Instance</span></span>  
 <span data-ttu-id="95bfe-110">Der `geography`-Datentyp stellt viele integrierte Methoden zur Verfügung, mit denen neue `geography`-Instanzen auf der Grundlage vorhandener Instanzen erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="95bfe-110">The `geography` data type provides numerous built-in methods you can use to create new `geography` instances based on existing instances.</span></span>  
  
 <span data-ttu-id="95bfe-111">**So erstellen Sie einen Puffer um eine geography**</span><span class="sxs-lookup"><span data-stu-id="95bfe-111">**To create a buffer around a geography**</span></span>  
 [<span data-ttu-id="95bfe-112">STBuffer &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-112">STBuffer &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stbuffer-geography-data-type)  
  
 <span data-ttu-id="95bfe-113">**So erstellen Sie einen Puffer um eine Geografie mit einer Toleranz**</span><span class="sxs-lookup"><span data-stu-id="95bfe-113">**To create a buffer around a geography, allowing for a tolerance**</span></span>  
 [<span data-ttu-id="95bfe-114">BufferWithTolerance &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-114">BufferWithTolerance &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/bufferwithtolerance-geography-data-type)  
  
 <span data-ttu-id="95bfe-115">**So erstellen Sie eine geography-Instanz aus der Schnittmenge von zwei geography-Instanzen**</span><span class="sxs-lookup"><span data-stu-id="95bfe-115">**To create a geography from the intersection of two geography instances**</span></span>  
 [<span data-ttu-id="95bfe-116">STIntersection &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-116">STIntersection &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stintersection-geography-data-type)  
  
 <span data-ttu-id="95bfe-117">**So erstellen Sie eine geography-Instanz aus der Vereinigung von zwei geography-Instanzen**</span><span class="sxs-lookup"><span data-stu-id="95bfe-117">**To create a geography from the union of two geography instances**</span></span>  
 [<span data-ttu-id="95bfe-118">STUnion &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-118">STUnion &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stunion-geography-data-type)  
  
 <span data-ttu-id="95bfe-119">**So erstellen Sie eine Geografie aus Punkten ohne überlappende Geografien**</span><span class="sxs-lookup"><span data-stu-id="95bfe-119">**To create a geography from the points where one geography does not overlap another**</span></span>  
 [<span data-ttu-id="95bfe-120">STDifference &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-120">STDifference &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stdifference-geography-data-type)  
  
###  <a name="constructing-a-geography-instance-from-well-known-text-input"></a><a name="wkt"></a> <span data-ttu-id="95bfe-121">Erstellen einer geography-Instanz anhand einer WKT-Eingabe (Well-Known Text)</span><span class="sxs-lookup"><span data-stu-id="95bfe-121">Constructing a geography Instance from Well-Known Text Input</span></span>  
 <span data-ttu-id="95bfe-122">Der `geography`-Datentyp bietet mehrere integrierte Methoden zur Erstellung einer Geografie anhand der WKT-Darstellung des Open Geospatial Consortium (OGC).</span><span class="sxs-lookup"><span data-stu-id="95bfe-122">The `geography` data type provides several built-in methods that generate a geography from the Open Geospatial Consortium (OGC) WKT representation.</span></span> <span data-ttu-id="95bfe-123">Der WKT-Standard ist eine Textzeichenfolge, die den Austausch von Geografiedaten in Textform ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="95bfe-123">The WKT standard is a text string that allows geography data to be exchanged in textual form.</span></span>  
  
 <span data-ttu-id="95bfe-124">**So erstellen Sie einen beliebigen geography-Instanztyp anhand einer WKT-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="95bfe-124">**To construct any type of geography instance from WKT input**</span></span>  
 [<span data-ttu-id="95bfe-125">STGeomFromText &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-125">STGeomFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeomfromtext-geography-data-type)  
  
 [<span data-ttu-id="95bfe-126">Parse &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-126">Parse &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/parse-geography-data-type)  
  
 <span data-ttu-id="95bfe-127">**So erstellen Sie eine Point-geography-Instanz anhand einer WKT-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="95bfe-127">**To construct a geography Point instance from WKT input**</span></span>  
 [<span data-ttu-id="95bfe-128">STPointFromText &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-128">STPointFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpointfromtext-geography-data-type)  
  
 <span data-ttu-id="95bfe-129">**So erstellen Sie eine MultiPoint-geography-Instanz anhand einer WKT-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="95bfe-129">**To construct a geography MultiPoint instance from WKT input**</span></span>  
 [<span data-ttu-id="95bfe-130">STMPointFromText &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-130">STMPointFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpointfromtext-geography-data-type)  
  
 <span data-ttu-id="95bfe-131">**So erstellen Sie eine LineString-geography-Instanz anhand einer WKT-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="95bfe-131">**To construct a geography LineString instance from WKT input**</span></span>  
 <span data-ttu-id="95bfe-132">STLineFromText (geography-Datentyp)</span><span class="sxs-lookup"><span data-stu-id="95bfe-132">STLineFromText (geography Data Type)</span></span>  
  
 <span data-ttu-id="95bfe-133">**So erstellen Sie eine MultiLineString-geography-Instanz anhand einer WKT-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="95bfe-133">**To construct a geography MultiLineString instance from WKT input**</span></span>  
 [<span data-ttu-id="95bfe-134">STMLineFromText &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-134">STMLineFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmlinefromtext-geography-data-type)  
  
 <span data-ttu-id="95bfe-135">**So erstellen Sie eine Polygon-geography-Instanz anhand einer WKT-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="95bfe-135">**To construct a geography Polygon instance from WKT input**</span></span>  
 [<span data-ttu-id="95bfe-136">STPolyFromText &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-136">STPolyFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpolyfromtext-geography-data-type)  
  
 <span data-ttu-id="95bfe-137">**So erstellen Sie eine MultiPolygon-geography-Instanz anhand einer WKT-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="95bfe-137">**To construct a geography MultiPolygon instance from WKT input**</span></span>  
 [<span data-ttu-id="95bfe-138">STMPolyFromText &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-138">STMPolyFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpolyfromtext-geography-data-type)  
  
 <span data-ttu-id="95bfe-139">**So erstellen Sie eine GeometryCollection-geography-Instanz anhand einer WKT-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="95bfe-139">**To construct a geography GeometryCollection instance from WKT input**</span></span>  
 [<span data-ttu-id="95bfe-140">STGeomCollFromText &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-140">STGeomCollFromText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeomcollfromtext-geography-data-type)  
  
###  <a name="constructing-a-geography-instance-from-well-known-binary-input"></a><a name="wkb"></a> <span data-ttu-id="95bfe-141">Erstellen einer geography-Instanz aus einer WKB-Eingabe (Well-Known Binary)</span><span class="sxs-lookup"><span data-stu-id="95bfe-141">Constructing a geography Instance from Well-Known Binary Input</span></span>  
 <span data-ttu-id="95bfe-142">WKB ist ein vom OGC spezifiziertes Binärformat, das den Austausch von `Geography`-Daten zwischen einer Clientanwendung und einer SQL-Datenbank ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="95bfe-142">WKB is a binary format specified by the OGC that permits `Geography` data to be exchanged between a client application and an SQL database.</span></span> <span data-ttu-id="95bfe-143">Die folgenden Funktionen akzeptieren die WKB-Eingabe zum Zweck der Erstellung von geography-Instanzen:</span><span class="sxs-lookup"><span data-stu-id="95bfe-143">The following functions accept WKB input to construct geography instances:</span></span>  
  
 <span data-ttu-id="95bfe-144">**So erstellen Sie einen beliebigen geography-Instanztyp anhand einer WKB-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="95bfe-144">**To construct any type of geography instance from WKB input**</span></span>  
 [<span data-ttu-id="95bfe-145">STGeomFromWKB &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-145">STGeomFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeomfromwkb-geography-data-type)  
  
 <span data-ttu-id="95bfe-146">**So erstellen Sie eine Point-geography-Instanz anhand einer WKB-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="95bfe-146">**To construct a geography Point instance from WKB input**</span></span>  
 [<span data-ttu-id="95bfe-147">STPointFromWKB &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-147">STPointFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpointfromwkb-geography-data-type)  
  
 <span data-ttu-id="95bfe-148">**So erstellen Sie eine MultiPoint-geography-Instanz anhand einer WKB-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="95bfe-148">**To construct a geography MultiPoint instance from WKB input**</span></span>  
 [<span data-ttu-id="95bfe-149">STMPointFromWKB &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-149">STMPointFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpointfromwkb-geography-data-type)  
  
 <span data-ttu-id="95bfe-150">**So erstellen Sie eine LineString-geography-Instanz anhand einer WKB-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="95bfe-150">**To construct a geography LineString instance from WKB input**</span></span>  
 [<span data-ttu-id="95bfe-151">STLineFromWKB &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-151">STLineFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stlinefromwkb-geography-data-type)  
  
 <span data-ttu-id="95bfe-152">**So erstellen Sie eine MultiLineString-geography-Instanz anhand einer WKB-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="95bfe-152">**To construct a geography MultiLineString instance from WKB input**</span></span>  
 [<span data-ttu-id="95bfe-153">STMLineFromWKB &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-153">STMLineFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmlinefromwkb-geography-data-type)  
  
 <span data-ttu-id="95bfe-154">**So erstellen Sie eine Polygon-geography-Instanz anhand einer WKB-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="95bfe-154">**To construct a geography Polygon instance from WKB input**</span></span>  
 [<span data-ttu-id="95bfe-155">STPolyFromWKB &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-155">STPolyFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stpolyfromwkb-geography-data-type)  
  
 <span data-ttu-id="95bfe-156">**So erstellen Sie eine MultiPolygon-geography-Instanz anhand einer WKB-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="95bfe-156">**To construct a geography MultiPolygon instance from WKB input**</span></span>  
 [<span data-ttu-id="95bfe-157">STMPolyFromWKB &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-157">STMPolyFromWKB &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stmpolyfromwkb-geography-data-type)  
  
 <span data-ttu-id="95bfe-158">**So erstellen Sie eine GeometryCollection-geography-Instanz anhand einer WKB-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="95bfe-158">**To construct a geography GeometryCollection instance from WKB input**</span></span>  
 <span data-ttu-id="95bfe-159">[STGeomCollFromWKB &#40;geography-Datentyp&#41;](/sql/t-sql/spatial-geography/stgeomcollfromwkb-geography-data-type)STGeomCollFromWKB (geography-Datentyp)</span><span class="sxs-lookup"><span data-stu-id="95bfe-159">[STGeomCollFromWKB &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stgeomcollfromwkb-geography-data-type)STGeomCollFromWKB (geography Data Type)</span></span>  
  
###  <a name="constructing-a-geography-instance-from-gml-text-input"></a><a name="gml"></a> <span data-ttu-id="95bfe-160">Erstellen einer geography-Instanz anhand einer GML-Texteingabe</span><span class="sxs-lookup"><span data-stu-id="95bfe-160">Constructing a geography Instance from GML Text Input</span></span>  
 <span data-ttu-id="95bfe-161">Der- `geography` Datentyp stellt eine Methode bereit, die eine- `geography` Instanz aus GML generiert, einer XML-Darstellung einer- `geography` Instanz.</span><span class="sxs-lookup"><span data-stu-id="95bfe-161">The `geography` data type provides a method that generates a `geography` instance from GML, an XML representation of a `geography` instance.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="95bfe-162">unterstützt eine Teilmenge von GML.</span><span class="sxs-lookup"><span data-stu-id="95bfe-162">supports a subset of GML.</span></span>  
  
 <span data-ttu-id="95bfe-163">Weitere Informationen über Geography Markup Language finden Sie in der OGC-Spezifikation: [OGC Specifications, Geography Markup Language.](https://go.microsoft.com/fwlink/?LinkId=93629)</span><span class="sxs-lookup"><span data-stu-id="95bfe-163">For more information on Geography Markup Language, see the OGC Specification: [OGC Specifications, Geography Markup Language.](https://go.microsoft.com/fwlink/?LinkId=93629)</span></span>  
  
 <span data-ttu-id="95bfe-164">**So erstellen Sie einen beliebigen geography-Instanztyp anhand einer GML-Eingabe**</span><span class="sxs-lookup"><span data-stu-id="95bfe-164">**To construct any type of geography instance from GML input**</span></span>  
 [<span data-ttu-id="95bfe-165">GeomFromGML &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-165">GeomFromGML &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/geomfromgml-geography-data-type)  
  
##  <a name="returning-well-known-text-and-well-known-binary-from-a-geography-instance"></a><a name="returning"></a> <span data-ttu-id="95bfe-166">Zurückgeben von WKT (Well-Known Text) oder WKB (Well-Known Binary) von einer geography-Instanz</span><span class="sxs-lookup"><span data-stu-id="95bfe-166">Returning Well-Known Text and Well-Known Binary from a geography Instance</span></span>  
 <span data-ttu-id="95bfe-167">Anhand der folgenden Methoden können Sie entweder das WKT- oder das WKB-Format einer `geography` zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="95bfe-167">You can use the following methods to return either the WKT or WKB format of a `geography` instance:</span></span>  
  
 <span data-ttu-id="95bfe-168">**So geben Sie die WKT-Darstellung einer geography-Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="95bfe-168">**To return the WKT representation of a geography instance**</span></span>  
 [<span data-ttu-id="95bfe-169">STAsText &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-169">STAsText &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stastext-geography-data-type)  
  
 [<span data-ttu-id="95bfe-170">ToString &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-170">ToString &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/tostring-geography-data-type)  
  
 <span data-ttu-id="95bfe-171">**So geben Sie eine WKT-Darstellung einer geography-Instanz einschließlich Z- und M-Werten zurück**</span><span class="sxs-lookup"><span data-stu-id="95bfe-171">**To return the WKT representation of a geography instance including any Z and M values**</span></span>  
 [<span data-ttu-id="95bfe-172">AsTextZM &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-172">AsTextZM &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/astextzm-geography-data-type)  
  
 <span data-ttu-id="95bfe-173">**So geben Sie die WKB-Darstellung einer geography-Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="95bfe-173">**To return the WKB representation of a geography instance**</span></span>  
 [<span data-ttu-id="95bfe-174">STAsBinary &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-174">STAsBinary &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stasbinary-geography-data-type)  
  
 <span data-ttu-id="95bfe-175">**So geben Sie eine GML-Darstellung einer geography-Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="95bfe-175">**To return a GML representation of a geography instance**</span></span>  
 [<span data-ttu-id="95bfe-176">AsGml &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-176">AsGml &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/asgml-geography-data-type)  
  
##  <a name="querying-the-properties-and-behaviors-of-geography-instances"></a><a name="query"></a> <span data-ttu-id="95bfe-177">Abfragen von Eigenschaften und Verhalten von geography-Instanzen</span><span class="sxs-lookup"><span data-stu-id="95bfe-177">Querying the Properties and Behaviors of geography Instances</span></span>  
 <span data-ttu-id="95bfe-178">Alle- `geography` Instanzen verfügen über eine Reihe von Eigenschaften, die über von bereitgestellte Methoden abgerufen werden können [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="95bfe-178">All `geography` instances have a number of properties that can be retrieved through methods that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides.</span></span> <span data-ttu-id="95bfe-179">In den folgenden Themen werden die Eigenschaften und Verhalten von geography-Typen und die Methoden zum Abrufen der einzelnen Eigenschaften und Verhalten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="95bfe-179">The following topics define the properties and behaviors of geography types, and the methods for querying each one.</span></span>  
  
###  <a name="validity-instance-type-and-geometrycollection-information"></a><a name="valid"></a> <span data-ttu-id="95bfe-180">Gültigkeit, Instanztyp und GeometryCollection-Informationen</span><span class="sxs-lookup"><span data-stu-id="95bfe-180">Validity, Instance Type, and GeometryCollection Information</span></span>  
 <span data-ttu-id="95bfe-181">Nachdem eine `geography`-Instanz erstellt wurde, können Sie anhand der folgenden Methoden den Instanztyp zurückgeben. Wenn es sich um eine `GeometryCollection`-Instanz handelt, können Sie eine bestimmte `geography`-Instanz zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="95bfe-181">After a `geography` instance is constructed, you can use the following methods to return the instance type, or if it is a `GeometryCollection` instance, return a specific `geography` instance.</span></span>  
  
 <span data-ttu-id="95bfe-182">**So geben Sie den Instanztyp einer Geografie zurück**</span><span class="sxs-lookup"><span data-stu-id="95bfe-182">**To return the instance type of a geography**</span></span>  
 [<span data-ttu-id="95bfe-183">STGeometryType &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-183">STGeometryType &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stgeometrytype-geography-data-type)  
  
 <span data-ttu-id="95bfe-184">**So bestimmen Sie, ob eine Geografie einen gegebenen Instanztyp aufweist**</span><span class="sxs-lookup"><span data-stu-id="95bfe-184">**To determine if a geography is a given instance type**</span></span>  
 [<span data-ttu-id="95bfe-185">InstanceOf &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-185">InstanceOf &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/instanceof-geography-data-type)  
  
 <span data-ttu-id="95bfe-186">**So bestimmen Sie, ob eine geography-Instanz für ihren Instanztyp wohlgeformt ist**</span><span class="sxs-lookup"><span data-stu-id="95bfe-186">**To determine if a geography instance is well-formed for its instance type**</span></span>  
 [<span data-ttu-id="95bfe-187">STNumGeometries &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-187">STNumGeometries &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stnumgeometries-geography-data-type)  
  
 <span data-ttu-id="95bfe-188">**So geben Sie eine bestimmte Geografie in einer GeometryCollection-Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="95bfe-188">**To return a specific geography in a GeometryCollection instance**</span></span>  
 <span data-ttu-id="95bfe-189">[STGeometryN &#40;geography-Datentyp&#41;](/sql/t-sql/spatial-geography/stgeometryn-geography-data-type)STGeometryN (geography-Datentyp)</span><span class="sxs-lookup"><span data-stu-id="95bfe-189">[STGeometryN &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stgeometryn-geography-data-type)STGeometryN (geography Data Type)</span></span>  
  
###  <a name="number-of-points"></a><a name="number"></a> <span data-ttu-id="95bfe-190">Anzahl von Punkten</span><span class="sxs-lookup"><span data-stu-id="95bfe-190">Number of Points</span></span>  
 <span data-ttu-id="95bfe-191">Alle nicht leeren `geography` Instanzen bestehen aus *Punkten*.</span><span class="sxs-lookup"><span data-stu-id="95bfe-191">All nonempty `geography` instances are comprised of *points*.</span></span> <span data-ttu-id="95bfe-192">Diese Punkte stellen den Längengrad und den Breitengrad der Erde dar, auf die die `geography`-Instanzen gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="95bfe-192">These points represent the latitude and longitude coordinates of the earth on which the `geography` instances are drawn.</span></span> <span data-ttu-id="95bfe-193">Der Datentyp `geography` stellt zahlreiche integrierte Methoden bereit zum Abfragen der Punkte einer Instanz.</span><span class="sxs-lookup"><span data-stu-id="95bfe-193">The data type `geography` provides numerous built-in methods for querying the points of an instance.</span></span>  
  
 <span data-ttu-id="95bfe-194">**So geben Sie die Anzahl von Punkten zurück, aus denen eine Instanz besteht**</span><span class="sxs-lookup"><span data-stu-id="95bfe-194">**To return the number of points that comprise an instance**</span></span>  
 [<span data-ttu-id="95bfe-195">STNumPoints &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-195">STNumPoints &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stnumpoints-geography-data-type)  
  
 <span data-ttu-id="95bfe-196">**So geben Sie einen bestimmten Punkt einer Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="95bfe-196">**To return a specific point in an instance**</span></span>  
 [<span data-ttu-id="95bfe-197">STPointN &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-197">STPointN &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type)  
  
 <span data-ttu-id="95bfe-198">**So geben Sie den Ausgangspunkt einer Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="95bfe-198">**To return the start point of an instance**</span></span>  
 [<span data-ttu-id="95bfe-199">STStartPoint &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-199">STStartPoint &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/ststartpoint-geography-data-type)  
  
 <span data-ttu-id="95bfe-200">**So geben Sie den Endpunkt einer Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="95bfe-200">**To return the end point of an instance**</span></span>  
 [<span data-ttu-id="95bfe-201">STEndpoint &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-201">STEndpoint &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stendpoint-geography-data-type)  
  
###  <a name="dimension"></a><a name="dimension"></a> <span data-ttu-id="95bfe-202">Dimension</span><span class="sxs-lookup"><span data-stu-id="95bfe-202">Dimension</span></span>  
 <span data-ttu-id="95bfe-203">Eine nicht leere `geography`-Instanz kann null-, ein- oder zweidimensional sein.</span><span class="sxs-lookup"><span data-stu-id="95bfe-203">A nonempty `geography` instance can be 0-, 1-, or 2-dimensional.</span></span> <span data-ttu-id="95bfe-204">NULL dimensionale `geography` Instanzen, wie z `Point` . b `MultiPoint` . und, haben keine Länge bzw. keinen Bereich.</span><span class="sxs-lookup"><span data-stu-id="95bfe-204">Zero-dimensional `geography` instances, such as `Point` and `MultiPoint`, have no length or area.</span></span> <span data-ttu-id="95bfe-205">Eindimensionale Objekte (z. B. `LineString, CircularString`, `CompoundCurve` und `MultiLineString`) weisen eine Länge auf.</span><span class="sxs-lookup"><span data-stu-id="95bfe-205">One-dimensional objects, such as `LineString, CircularString`, `CompoundCurve`, and `MultiLineString`, have length.</span></span> <span data-ttu-id="95bfe-206">Zweidimensionale Instanzen (z. B. `Polygon, CurvePolygon` und `MultiPolygon`) weisen eine Fläche und eine Länge auf.</span><span class="sxs-lookup"><span data-stu-id="95bfe-206">Two-dimensional instances, such as `Polygon, CurvePolygon`, and `MultiPolygon`, have area and length.</span></span> <span data-ttu-id="95bfe-207">Für leere Instanzen wird als Dimension -1 ausgegeben, und für eine `GeometryCollection`-Auflistung wird die maximale Dimension der darin enthaltenen Elemente zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="95bfe-207">Empty instances report a dimension of -1, and a `GeometryCollection` reports the maximum dimension of its contents.</span></span>  
  
 <span data-ttu-id="95bfe-208">**So geben Sie die Dimension einer Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="95bfe-208">**To return the dimension of an instance**</span></span>  
 [<span data-ttu-id="95bfe-209">STDimension &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-209">STDimension &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stdimension-geography-data-type)  
  
 <span data-ttu-id="95bfe-210">**So geben Sie die Länge einer Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="95bfe-210">**To return the length of an instance**</span></span>  
 [<span data-ttu-id="95bfe-211">STLength &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-211">STLength &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stlength-geography-data-type)  
  
 <span data-ttu-id="95bfe-212">**So geben Sie die Fläche einer Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="95bfe-212">**To return the area of an instance**</span></span>  
 [<span data-ttu-id="95bfe-213">STArea &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-213">STArea &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/starea-geography-data-type)  
  
###  <a name="empty"></a><a name="empty"></a> <span data-ttu-id="95bfe-214">Empty</span><span class="sxs-lookup"><span data-stu-id="95bfe-214">Empty</span></span>  
 <span data-ttu-id="95bfe-215">Eine *leere* - `geography` Instanz besitzt keine Punkte.</span><span class="sxs-lookup"><span data-stu-id="95bfe-215">An *empty*`geography` instance does not have any points.</span></span> <span data-ttu-id="95bfe-216">Die Länge von leeren `LineString, CircularString`-, `CompoundCurve`- und `MultiLineString`-Instanzen ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="95bfe-216">The length of empty `LineString, CircularString`, `CompoundCurve`, and `MultiLineString` instances is 0.</span></span> <span data-ttu-id="95bfe-217">Die Fläche von leeren `Polygon, CurvePolygon`- und `MultiPolygon`-Instanzen ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="95bfe-217">The area of empty `Polygon, CurvePolygon` and `MultiPolygon` instances is 0.</span></span>  
  
 <span data-ttu-id="95bfe-218">**So bestimmen Sie, ob eine Instanz leer ist**</span><span class="sxs-lookup"><span data-stu-id="95bfe-218">**To determine if an instance is empty**</span></span>  
 [<span data-ttu-id="95bfe-219">STIsEmpty &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-219">STIsEmpty &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stisempty-geography-data-type)  
  
###  <a name="closure"></a><a name="closure"></a> <span data-ttu-id="95bfe-220">Abgeschlossenheit</span><span class="sxs-lookup"><span data-stu-id="95bfe-220">Closure</span></span>  
 <span data-ttu-id="95bfe-221">Eine *geschlossene* - `geography` Instanz ist eine Abbildung, deren Start-und Endpunkte identisch sind.</span><span class="sxs-lookup"><span data-stu-id="95bfe-221">A *closed*`geography` instance is a figure whose start points and end points are the same.</span></span> <span data-ttu-id="95bfe-222">Alle `Polygon`-Instanzen gelten als geschlossen.</span><span class="sxs-lookup"><span data-stu-id="95bfe-222">`Polygon` instances are considered closed.</span></span> <span data-ttu-id="95bfe-223">Alle `Point`-Instanzen gelten als nicht geschlossen.</span><span class="sxs-lookup"><span data-stu-id="95bfe-223">`Point` instances are not closed.</span></span>  
  
 <span data-ttu-id="95bfe-224">Ein Ring ist eine einfache, geschlossene `LineString`-Instanz.</span><span class="sxs-lookup"><span data-stu-id="95bfe-224">A ring is a simple, closed `LineString` instance.</span></span>  
  
 <span data-ttu-id="95bfe-225">**So bestimmen Sie, ob eine Instanz abgeschlossen ist**</span><span class="sxs-lookup"><span data-stu-id="95bfe-225">**To determine if an instance is closed**</span></span>  
 [<span data-ttu-id="95bfe-226">STIsClosed &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-226">STIsClosed &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stisclosed-geography-data-type)  
  
 <span data-ttu-id="95bfe-227">**So geben Sie die Anzahl von Ringen in einer Polygoninstanz zurück**</span><span class="sxs-lookup"><span data-stu-id="95bfe-227">**To return the number of rings in a Polygon instance**</span></span>  
 [<span data-ttu-id="95bfe-228">NumRings &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-228">NumRings &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/numrings-geography-data-type)  
  
 <span data-ttu-id="95bfe-229">**So geben Sie einen gegebenen Ring einer geography-Instanz zurück**</span><span class="sxs-lookup"><span data-stu-id="95bfe-229">**To return a specified ring of a geography instance**</span></span>  
 [<span data-ttu-id="95bfe-230">RingN &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-230">RingN &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/ringn-geography-data-type)  
  
###  <a name="spatial-reference-id-srid"></a><a name="srid"></a> <span data-ttu-id="95bfe-231">SRID (Spatial Reference ID)</span><span class="sxs-lookup"><span data-stu-id="95bfe-231">Spatial Reference ID (SRID)</span></span>  
 <span data-ttu-id="95bfe-232">Der SRID (Spatial Reference ID) ist ein Bezeichner, der das ellipsenförmige Koordinatensystem angibt, in dem die `geography`-Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="95bfe-232">The spatial reference ID (SRID) is an identifier specifying which ellipsoidal coordinate system the `geography` instance is represented in.</span></span> <span data-ttu-id="95bfe-233">Zwei `geography`-Instanzen mit unterschiedlichen SRIDs können nicht verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="95bfe-233">Two `geography` instances with different SRIDs cannot be compared.</span></span>  
  
 <span data-ttu-id="95bfe-234">**So können Sie die SRID einer Instanz festlegen oder zurückgeben**</span><span class="sxs-lookup"><span data-stu-id="95bfe-234">**To set or return the SRID of an instance**</span></span>  
 [<span data-ttu-id="95bfe-235">STSrid &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-235">STSrid &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stsrid-geography-data-type)  
  
 <span data-ttu-id="95bfe-236">Diese Eigenschaft kann geändert werden.</span><span class="sxs-lookup"><span data-stu-id="95bfe-236">This property can be modified.</span></span>  
  
##  <a name="determining-relationships-between-geography-instances"></a><a name="rel"></a> <span data-ttu-id="95bfe-237">Bestimmen von Beziehungen zwischen geography-Instanzen</span><span class="sxs-lookup"><span data-stu-id="95bfe-237">Determining Relationships between geography Instances</span></span>  
 <span data-ttu-id="95bfe-238">Der `geography`-Datentyp stellt viele integrierte Methoden zur Verfügung, mit denen die Beziehungen zwischen zwei `geography`-Instanzen bestimmt werden können.</span><span class="sxs-lookup"><span data-stu-id="95bfe-238">The `geography` data type provides many built-in methods you can use to determine relationships between two `geography` instances.</span></span>  
  
 <span data-ttu-id="95bfe-239">**So bestimmen Sie, ob zwei Instanzen die gleiche Punktmenge umfassen**</span><span class="sxs-lookup"><span data-stu-id="95bfe-239">**To determine if two instances comprise the same point set**</span></span>  
 [<span data-ttu-id="95bfe-240">STEquals &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-240">STEquals &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stequals-geometry-data-type)  
  
 <span data-ttu-id="95bfe-241">**So bestimmen Sie, ob zwei Instanzen disjunkt sind**</span><span class="sxs-lookup"><span data-stu-id="95bfe-241">**To determine if two instances are disjoint**</span></span>  
 [<span data-ttu-id="95bfe-242">STDisjoint &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-242">STDisjoint &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stdisjoint-geometry-data-type)  
  
 <span data-ttu-id="95bfe-243">**So bestimmen Sie, ob sich zwei Instanzen überschneiden**</span><span class="sxs-lookup"><span data-stu-id="95bfe-243">**To determine if two instances intersect**</span></span>  
 [<span data-ttu-id="95bfe-244">STIntersects &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-244">STIntersects &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stintersects-geometry-data-type)  
  
 <span data-ttu-id="95bfe-245">**So bestimmen Sie den Punkt bzw. die Punkte, an dem bzw. denen sich zwei Instanzen überschneiden**</span><span class="sxs-lookup"><span data-stu-id="95bfe-245">**To determine the point or points where two instances intersect**</span></span>  
 [<span data-ttu-id="95bfe-246">STIntersection &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-246">STIntersection &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stintersection-geography-data-type)  
  
 <span data-ttu-id="95bfe-247">**So bestimmen Sie die kürzeste Entfernung zwischen Punkten in zwei geography-Instanzen**</span><span class="sxs-lookup"><span data-stu-id="95bfe-247">**To determine the shortest distance between points in two geography instances**</span></span>  
 [<span data-ttu-id="95bfe-248">STDistance &#40;geometry-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-248">STDistance &#40;geometry Data Type&#41;</span></span>](/sql/t-sql/spatial-geometry/stdistance-geometry-data-type)  
  
 <span data-ttu-id="95bfe-249">**So bestimmen Sie zwischen zwei geography-Instanzen bestehende die Differenz in Punkten**</span><span class="sxs-lookup"><span data-stu-id="95bfe-249">**To determine the difference in points between two geography instances**</span></span>  
 [<span data-ttu-id="95bfe-250">STDifference &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-250">STDifference &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stdifference-geography-data-type)  
  
 <span data-ttu-id="95bfe-251">**So leiten Sie die symmetrische Differenz oder eindeutigen Punkte einer geography-Instanz ab, die mit einer anderen Instanz verglichen wird**</span><span class="sxs-lookup"><span data-stu-id="95bfe-251">**To derive the symmetric difference, or unique points, of one geography instance compared with another instance**</span></span>  
 [<span data-ttu-id="95bfe-252">STSymDifference &#40;geography-Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-252">STSymDifference &#40;geography Data Type&#41;</span></span>](/sql/t-sql/spatial-geography/stsymdifference-geography-data-type)  
  
##  <a name="geography-instances-must-use-supported-srid"></a><a name="supportedsrid"></a> <span data-ttu-id="95bfe-253">geography-Instanzen müssen unterstützte SRIDs verwenden</span><span class="sxs-lookup"><span data-stu-id="95bfe-253">geography Instances Must Use Supported SRID</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="95bfe-254">unterstützt SRIDs auf der Grundlage der EPSG-Standards.</span><span class="sxs-lookup"><span data-stu-id="95bfe-254">supports SRIDs based on the EPSG standards.</span></span> <span data-ttu-id="95bfe-255">Wenn Berechnungen mit geografischen räumlichen Daten ausgeführt werden oder Methoden mit geografischen räumlichen Daten verwendet werden, müssen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützte SRIDs für `geography`-Instanzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="95bfe-255">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-supported SRID for `geography` instances must be used when performing calculations or using methods with geography spatial data.</span></span> <span data-ttu-id="95bfe-256">Die SRID muss mit einer der SRIDs übereinstimmen, die in der **sys.spatial_reference_systems** -Katalogsicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="95bfe-256">The SRID must match one of the SRIDs displayed in the **sys.spatial_reference_systems** catalog view.</span></span> <span data-ttu-id="95bfe-257">Wie bereits erwähnt, hängen die Ergebnisse von Berechnungen mit räumlichen Daten unter Verwendung des `geography`-Datentyps von der Ellipsenform ab, die zur Erstellung der Daten verwendet wurde, da jeder Ellipsenform ein bestimmter SRID zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="95bfe-257">As mentioned previously, when you perform calculations on your spatial data using the `geography` data type, your results will depend on which ellipsoid was used in the creation of your data, as each ellipsoid is assigned a specific spatial reference identifier (SRID).</span></span>  
  
 <span data-ttu-id="95bfe-258">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird beim Einsatz von Methoden für `geography`-Instanzen standardmäßig der SRID 4326 verwendet, der dem räumlichen Referenzsystem WGS 84 zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="95bfe-258">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the default SRID of 4326, which maps to the WGS 84 spatial reference system, when using methods on `geography` instances.</span></span> <span data-ttu-id="95bfe-259">Wenn Sie Daten aus einem anderen räumlichen Referenzsystem als WGS 84 (bzw. SRID 4326) verwenden, müssen Sie die SRID dieser geografischen räumlichen Daten bestimmen.</span><span class="sxs-lookup"><span data-stu-id="95bfe-259">If you use data from a spatial reference system other than WGS 84 (or SRID 4326), you will need to determine the specific SRID for your geography spatial data.</span></span>  
  
##  <a name="examples"></a><a name="examples"></a> <span data-ttu-id="95bfe-260">Beispiele</span><span class="sxs-lookup"><span data-stu-id="95bfe-260">Examples</span></span>  
 <span data-ttu-id="95bfe-261">Die folgenden Beispiele zeigen, wie Geografiedaten hinzugefügt und abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="95bfe-261">The following examples show how to add and query geography data.</span></span>  
  
-   <span data-ttu-id="95bfe-262">Im ersten Beispiel wird eine Tabelle mit einer Identitätsspalte und der `geography` -Spalte `GeogCol1`erstellt.</span><span class="sxs-lookup"><span data-stu-id="95bfe-262">The first example creates a table with an identity column and a `geography` column `GeogCol1`.</span></span> <span data-ttu-id="95bfe-263">Eine dritte Spalte rendert die `geography` -Spalte als Darstellung im Open Geospatial Consortium (OGC) WKT-Format und verwendet die `STAsText()` -Methode.</span><span class="sxs-lookup"><span data-stu-id="95bfe-263">A third column renders the `geography` column into its Open Geospatial Consortium (OGC) Well-Known Text (WKT) representation, and uses the `STAsText()` method.</span></span> <span data-ttu-id="95bfe-264">Dann werden zwei Zeilen eingefügt: Eine Zeile enthält eine `LineString` -Instanz des Typs `geography`und die andere eine `Polygon` -Instanz.</span><span class="sxs-lookup"><span data-stu-id="95bfe-264">Two rows are then inserted: one row contains a `LineString` instance of `geography`, and one row contains a `Polygon` instance.</span></span>  
  
    ```  
    IF OBJECT_ID ( 'dbo.SpatialTable', 'U' ) IS NOT NULL   
        DROP TABLE dbo.SpatialTable;  
    GO  
  
    CREATE TABLE SpatialTable   
        ( id int IDENTITY (1,1),  
        GeogCol1 geography,   
        GeogCol2 AS GeogCol1.STAsText() );  
    GO  
  
    INSERT INTO SpatialTable (GeogCol1)  
    VALUES (geography::STGeomFromText('LINESTRING(-122.360 47.656, -122.343 47.656)', 4326));  
  
    INSERT INTO SpatialTable (GeogCol1)  
    VALUES (geography::STGeomFromText('POLYGON((-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))', 4326));  
    GO  
    ```  
  
-   <span data-ttu-id="95bfe-265">Im zweiten Beispiel werden mithilfe der `STIntersection()` -Methode die Punkte zurückgegeben, an denen die beiden zuvor eingegebenen `geography` -Instanzen sich schneiden.</span><span class="sxs-lookup"><span data-stu-id="95bfe-265">The second example uses the `STIntersection()` method to return the points where the two previously inserted `geography` instances intersect.</span></span>  
  
    ```  
    DECLARE @geog1 geography;  
    DECLARE @geog2 geography;  
    DECLARE @result geography;  
  
    SELECT @geog1 = GeogCol1 FROM SpatialTable WHERE id = 1;  
    SELECT @geog2 = GeogCol1 FROM SpatialTable WHERE id = 2;  
    SELECT @result = @geog1.STIntersection(@geog2);  
    SELECT @result.STAsText();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="95bfe-266">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95bfe-266">See Also</span></span>  
 [<span data-ttu-id="95bfe-267">Räumliche Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="95bfe-267">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
