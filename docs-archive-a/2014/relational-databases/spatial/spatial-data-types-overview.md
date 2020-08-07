---
title: Übersicht über räumliche Datentypen | Microsoft-Dokumentation
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geometry data type [SQL Server], understanding
- geography data type [SQL Server], spatial data
- planar spatial data [SQL Server], geometry data type
- spatial data types [SQL Server]
ms.assetid: 1615db50-69de-4778-8be6-4e058c00ccd4
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: c0548d974e83bfe2b1e103d4458b17078fba8014
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719759"
---
# <a name="spatial-data-types-overview"></a><span data-ttu-id="e7567-102">Übersicht über räumliche Datentypen</span><span class="sxs-lookup"><span data-stu-id="e7567-102">Spatial Data Types Overview</span></span>
  <span data-ttu-id="e7567-103">Es gibt zwei Typen von räumlichen Daten.</span><span class="sxs-lookup"><span data-stu-id="e7567-103">There are two types of spatial data.</span></span> <span data-ttu-id="e7567-104">Der `geometry`-Datentyp unterstützt planare bzw. euklidische Daten.</span><span class="sxs-lookup"><span data-stu-id="e7567-104">The `geometry` data type supports planar, or Euclidean (flat-earth), data.</span></span> <span data-ttu-id="e7567-105">Der `geometry`-Datentyp entspricht der Open Geospatial Consortium (OGC) Simple Features for SQL Specification Version 1.1.0. und ist auch mit SQL MM (ISO-Standard) kompatibel.</span><span class="sxs-lookup"><span data-stu-id="e7567-105">The `geometry` data type both conforms to the Open Geospatial Consortium (OGC) Simple Features for SQL Specification version 1.1.0 and is compliant with SQL MM (ISO standard).</span></span>

 <span data-ttu-id="e7567-106">Zudem unterstützt [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] den `geography`-Datentyp, der ellipsenförmige Daten speichert, z. B. GPS-Breiten- und Längenkoordinaten.</span><span class="sxs-lookup"><span data-stu-id="e7567-106">In addition, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] supports the `geography` data type, which stores ellipsoidal (round-earth) data, such as GPS latitude and longitude coordinates.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="e7567-107">Laden Sie für eine ausführliche Beschreibung und Beispiele der in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]eingeführten räumlichen Funktionen (z.B. Erweiterungen der räumlichen Datentypen) das folgende Whitepaper herunter: [New Spatial Features in SQL Server Code-Named „Denali“](https://go.microsoft.com/fwlink/?LinkId=226407)(Neue räumliche Funktionen in SQL Server Codename „Denali“).</span><span class="sxs-lookup"><span data-stu-id="e7567-107">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including enhancements to the spatial data types, download the white paper, [New Spatial Features in SQL Server Code-Named "Denali"](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>

##  <a name="spatial-data-objects"></a><a name="objects"></a> <span data-ttu-id="e7567-108">Räumliche Datenobjekte</span><span class="sxs-lookup"><span data-stu-id="e7567-108">Spatial Data Objects</span></span>
 <span data-ttu-id="e7567-109">Der `geometry`-Datentyp und der `geography`-Datentyp unterstützen 16 räumliche Datenobjekte bzw. Instanztypen.</span><span class="sxs-lookup"><span data-stu-id="e7567-109">The `geometry` and `geography` data types support sixteen spatial data objects, or instance types.</span></span> <span data-ttu-id="e7567-110">Nur elf dieser Instanztypen sind jedoch *instanziierbar*. Sie können diese Instanzen erstellen und Sie in einer Datenbanken bearbeiten (oder instanziieren).</span><span class="sxs-lookup"><span data-stu-id="e7567-110">However, only eleven of these instance types are *instantiable*; you can create and work with these instances (or instantiate them) in a database.</span></span> <span data-ttu-id="e7567-111">Diese Instanzen leiten bestimmte Eigenschaften von ihren übergeordneten Datentypen ab, die Sie als `Points` , **LineString, circularstrings**, `CompoundCurves` , `Polygons` `CurvePolygons` oder als mehrere- `geometry` oder- `geography` Instanzen in einer `GeometryCollection` unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="e7567-111">These instances derive certain properties from their parent data types that distinguish them as `Points`, **LineStrings, CircularStrings**, `CompoundCurves`, `Polygons`, `CurvePolygons` or as multiple `geometry` or `geography` instances in a `GeometryCollection`.</span></span> <span data-ttu-id="e7567-112">Der `Geography`-Typ verfügt über einen zusätzlichen Instanztyp `FullGlobe`.</span><span class="sxs-lookup"><span data-stu-id="e7567-112">`Geography` type has an additional instance type, `FullGlobe`.</span></span>

 <span data-ttu-id="e7567-113">Die nachfolgende Abbildung stellt die `geometry`-Hierarchie dar, auf der der `geometry`-Datentyp und der `geography`-Datentyp basieren.</span><span class="sxs-lookup"><span data-stu-id="e7567-113">The figure below depicts the `geometry` hierarchy upon which the `geometry` and `geography` data types are based.</span></span> <span data-ttu-id="e7567-114">Die instanziier baren Typen von `geometry` und `geography` sind blau dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e7567-114">The instantiable types of `geometry` and `geography` are indicated in blue.</span></span>

 <span data-ttu-id="e7567-115">![Hierarchie des Geometrietyps](../../database-engine/media/geom-hierarchy.gif "Hierarchie des Geometrietyps")</span><span class="sxs-lookup"><span data-stu-id="e7567-115">![Hierarchy of the geometry type](../../database-engine/media/geom-hierarchy.gif "Hierarchy of the geometry type")</span></span>

 <span data-ttu-id="e7567-116">Wie die Abbildung zeigt, sind die zehn instanziier baren Typen `geometry` der `geography` Datentypen und `Point` , `MultiPoint` , `LineString` , `CircularString` , `MultiLineString` , `CompoundCurve` , `Polygon` , `CurvePolygon` , `MultiPolygon` und `GeometryCollection` .</span><span class="sxs-lookup"><span data-stu-id="e7567-116">As the figure indicates, the ten instantiable types of the `geometry` and `geography` data types are `Point`, `MultiPoint`, `LineString`, `CircularString`, `MultiLineString`, `CompoundCurve`, `Polygon`, `CurvePolygon`, `MultiPolygon`, and `GeometryCollection`.</span></span> <span data-ttu-id="e7567-117">Es gibt einen zusätzlichen instanziierbaren Typen für den geography-Datentyp: `FullGlobe`.</span><span class="sxs-lookup"><span data-stu-id="e7567-117">There is one additional instantiable type for the geography data type: `FullGlobe`.</span></span> <span data-ttu-id="e7567-118">Der `geometry` -Typ und der- `geography` Typ können eine bestimmte-Instanz erkennen, solange es sich um eine wohlgeformte Instanz handelt, auch wenn die-Instanz nicht explizit definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e7567-118">The `geometry` and `geography` types can recognize a specific instance as long as it is a well-formed instance, even if the instance is not defined explicitly.</span></span> <span data-ttu-id="e7567-119">Wenn Sie z. b. eine `Point` -Instanz explizit mit der STPointFromText ()-Methode definieren `geometry` und `geography` die-Instanz als eine erkennen `Point` , sofern die Methoden Eingabe wohl geformt ist.</span><span class="sxs-lookup"><span data-stu-id="e7567-119">For example, if you define a `Point` instance explicitly using the STPointFromText() method, `geometry` and `geography` recognize the instance as a `Point`, as long as the method input is well-formed.</span></span> <span data-ttu-id="e7567-120">Wenn Sie die gleiche Instanz mit der `STGeomFromText()`-Methode definieren, erkennen sowohl der `geometry`-Datentyp als auch der `geography`-Datentyp die Instanz als `Point`.</span><span class="sxs-lookup"><span data-stu-id="e7567-120">If you define the same instance using the `STGeomFromText()` method, both the `geometry` and `geography` data types recognize the instance as a `Point`.</span></span>

 <span data-ttu-id="e7567-121">Die Untertypen für geometry- und geography-Typen sind in einfache Typen und Auflistungstypen unterteilt.</span><span class="sxs-lookup"><span data-stu-id="e7567-121">The subtypes for geometry and geography types are divided into simple and collection types.</span></span>  <span data-ttu-id="e7567-122">Einige Methoden wie `STNumCurves()` funktionieren nur mit einfachen Typen.</span><span class="sxs-lookup"><span data-stu-id="e7567-122">Some methods like `STNumCurves()` work only with simple types.</span></span>

 <span data-ttu-id="e7567-123">Zu einfachen Typen gehören:</span><span class="sxs-lookup"><span data-stu-id="e7567-123">Simple types include:</span></span>

-   [<span data-ttu-id="e7567-124">Point</span><span class="sxs-lookup"><span data-stu-id="e7567-124">Point</span></span>](../spatial/point.md)

-   [<span data-ttu-id="e7567-125">LineString</span><span class="sxs-lookup"><span data-stu-id="e7567-125">LineString</span></span>](../spatial/linestring.md)

-   [<span data-ttu-id="e7567-126">CircularString</span><span class="sxs-lookup"><span data-stu-id="e7567-126">CircularString</span></span>](../spatial/circularstring.md)

-   [<span data-ttu-id="e7567-127">CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="e7567-127">CompoundCurve</span></span>](../spatial/compoundcurve.md)

-   [<span data-ttu-id="e7567-128">Polygon</span><span class="sxs-lookup"><span data-stu-id="e7567-128">Polygon</span></span>](../spatial/polygon.md)

-   [<span data-ttu-id="e7567-129">CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="e7567-129">CurvePolygon</span></span>](../spatial/curvepolygon.md)

 <span data-ttu-id="e7567-130">Zu Auflistungstypen gehören:</span><span class="sxs-lookup"><span data-stu-id="e7567-130">Collection types include:</span></span>

-   [<span data-ttu-id="e7567-131">MultiPoint</span><span class="sxs-lookup"><span data-stu-id="e7567-131">MultiPoint</span></span>](../spatial/multipoint.md)

-   [<span data-ttu-id="e7567-132">MultiLineString</span><span class="sxs-lookup"><span data-stu-id="e7567-132">MultiLineString</span></span>](../spatial/multilinestring.md)

-   [<span data-ttu-id="e7567-133">MultiPolygon</span><span class="sxs-lookup"><span data-stu-id="e7567-133">MultiPolygon</span></span>](../spatial/multipolygon.md)

-   [<span data-ttu-id="e7567-134">GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="e7567-134">GeometryCollection</span></span>](../spatial/geometrycollection.md)


##  <a name="differences-between-the-geometry-and-geography-data-types"></a><a name="differences"></a> <span data-ttu-id="e7567-135">Unterschiede zwischen den geometry- und geography-Datentypen</span><span class="sxs-lookup"><span data-stu-id="e7567-135">Differences Between the geometry and geography Data Types</span></span>
 <span data-ttu-id="e7567-136">Die beiden Typen von räumlichen Daten verhalten sich oft ganz ähnlich. Es gibt aber einige wichtige Unterschiede in Bezug darauf, wie Daten gespeichert und bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="e7567-136">The two types of spatial data often behave quite similarly, but there are some key differences in how the data is stored and manipulated.</span></span>

### <a name="how-connecting-edges-are-defined"></a><span data-ttu-id="e7567-137">Definieren von verbindenden Rändern</span><span class="sxs-lookup"><span data-stu-id="e7567-137">How connecting edges are defined</span></span>
 <span data-ttu-id="e7567-138">Die definierenden Daten für die Typen `LineString` und `Polygon` sind nur Scheitelpunkte.</span><span class="sxs-lookup"><span data-stu-id="e7567-138">The defining data for `LineString` and `Polygon` types are vertices only.</span></span>  <span data-ttu-id="e7567-139">Der verbindende Rand zwischen zwei Scheitelpunkten in einer Geometrie ist eine gerade Linie.</span><span class="sxs-lookup"><span data-stu-id="e7567-139">The connecting edge between two vertices in a geometry type is a straight line.</span></span>  <span data-ttu-id="e7567-140">Die verbindende Kante zwischen zwei Scheitelpunkten in einem Geografietyp ist ein kurzer elliptischer Bogen zwischen den beiden Scheitelpunkten.</span><span class="sxs-lookup"><span data-stu-id="e7567-140">However, the connecting edge between two vertices in a geography type is a short great elliptic arc between the two vertices.</span></span>  <span data-ttu-id="e7567-141">Eine große Ellipse ist die Schnittmenge des Ellipsoids mit einer Ebene durch seinen Mittelpunkt, und ein großer elliptischer Bogen ist ein Bogensegment auf der großen Ellipse.</span><span class="sxs-lookup"><span data-stu-id="e7567-141">A great ellipse is the intersection of the ellipsoid with a plane through its center and a great elliptic arc is an arc segment on the great ellipse.</span></span>

### <a name="how-circular-arc-segments-are-defined"></a><span data-ttu-id="e7567-142">Definieren von Kreisbogensegmenten</span><span class="sxs-lookup"><span data-stu-id="e7567-142">How circular arc segments are defined</span></span>
 <span data-ttu-id="e7567-143">Kreisbogensegmente für geometry-Typen werden in der kartesischen XY-Koordinatenebene definiert (Z-Werte werden ignoriert).</span><span class="sxs-lookup"><span data-stu-id="e7567-143">Circular arc segments for geometry types are defined on the XY Cartesian coordinate plane (Z values are ignored).</span></span> <span data-ttu-id="e7567-144">Kreisbogensegmente für geography-Typen werden von Kurvenabschnitten auf einer Verweiskugel definiert.</span><span class="sxs-lookup"><span data-stu-id="e7567-144">Circular arc segments for geography types are defined by curve segments on a reference sphere.</span></span> <span data-ttu-id="e7567-145">Jede Parallele auf der Verweiskugel kann von zwei komplementären Kreisbögen definiert werden, wobei die Punkte für beide Bögen einen konstanten Breitenwinkel haben.</span><span class="sxs-lookup"><span data-stu-id="e7567-145">Any parallel on the reference sphere can be defined by two complementary circular arcs where the points for both arcs have a constant latitude angle.</span></span>

### <a name="measurements-in-spatial-data-types"></a><span data-ttu-id="e7567-146">Maße in räumlichen Datentypen</span><span class="sxs-lookup"><span data-stu-id="e7567-146">Measurements in spatial data types</span></span>
 <span data-ttu-id="e7567-147">Im planaren bzw. euklidischen System werden Maße von Entfernungen und Flächen in der gleichen Maßeinheit angegeben wie die Koordinaten.</span><span class="sxs-lookup"><span data-stu-id="e7567-147">In the planar, or flat-earth, system, measurements of distances and areas are given in the same unit of measurement as coordinates.</span></span> <span data-ttu-id="e7567-148">Bei Verwendung des `geometry`-Datentyps beträgt die Entfernung zwischen (2, 2) und (5, 6) ungeachtet der verwendeten Maßeinheit 5 Einheiten.</span><span class="sxs-lookup"><span data-stu-id="e7567-148">Using the `geometry` data type, the distance between (2, 2) and (5, 6) is 5 units, regardless of the units used.</span></span>

 <span data-ttu-id="e7567-149">Im ellipsenförmigen System werden Koordinaten in Breiten- und Längengraden angegeben.</span><span class="sxs-lookup"><span data-stu-id="e7567-149">In the ellipsoidal, or round-earth system, coordinates are given in degrees of latitude and longitude.</span></span> <span data-ttu-id="e7567-150">Längen und Flächen werden in der Regel in Meter und Quadratmeter gemessen. Die Maßeinheit kann jedoch vom SRID der `geography`-Instanz abhängen.</span><span class="sxs-lookup"><span data-stu-id="e7567-150">However, lengths and areas are usually measured in meters and square meters, though the measurement may depend on the spatial reference identifier (SRID) of the `geography` instance.</span></span> <span data-ttu-id="e7567-151">Die gängigste Maßeinheit für den `geography`-Datentyp ist Meter.</span><span class="sxs-lookup"><span data-stu-id="e7567-151">The most common unit of measurement for the `geography` data type is meters.</span></span>

### <a name="orientation-of-spatial-data"></a><span data-ttu-id="e7567-152">Ausrichtung von räumlichen Daten</span><span class="sxs-lookup"><span data-stu-id="e7567-152">Orientation of spatial data</span></span>
 <span data-ttu-id="e7567-153">Im planaren System ist die Ringausrichtung eines Polygons kein wichtiger Faktor.</span><span class="sxs-lookup"><span data-stu-id="e7567-153">In the planar system, the ring orientation of a polygon is not an important factor.</span></span> <span data-ttu-id="e7567-154">Beispielsweise entspricht das durch ((0, 0), (10, 0), (0, 20), (0, 0)) gegebene Polygon dem Polygon, das durch ((0, 0), (0, 20), (10, 0), (0, 0)) beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="e7567-154">For example, a polygon described by ((0, 0), (10, 0), (0, 20), (0, 0)) is the same as a polygon described by ((0, 0), (0, 20), (10, 0), (0, 0)).</span></span> <span data-ttu-id="e7567-155">Die OGC Simple Features for SQL-Spezifikation schreibt keine Ringreihenfolge vor, und [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] erzwingt keine Ringreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="e7567-155">The OGC Simple Features for SQL Specification does not dictate a ring ordering, and [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] does not enforce ring ordering.</span></span>

 <span data-ttu-id="e7567-156">In einem ellipsenförmigen System hat ein Polygon ohne Ausrichtung keine Bedeutung bzw. ist mehrdeutig.</span><span class="sxs-lookup"><span data-stu-id="e7567-156">In an ellipsoidal system, a polygon has no meaning, or is ambiguous, without an orientation.</span></span> <span data-ttu-id="e7567-157">Beschreibt beispielsweise ein Ring um den Äquator die nördliche oder die südliche Hemisphäre?</span><span class="sxs-lookup"><span data-stu-id="e7567-157">For example, does a ring around the equator describe the northern or southern hemisphere?</span></span> <span data-ttu-id="e7567-158">Wenn wir den `geography`-Datentyp zum Speichern von räumlichen Daten verwenden, müssen wir die Ausrichtung des Rings angeben und die Position der Instanz genau beschreiben.</span><span class="sxs-lookup"><span data-stu-id="e7567-158">If we use the `geography` data type to store the spatial instance, we must specify the orientation of the ring and accurately describe the location of the instance.</span></span> <span data-ttu-id="e7567-159">Der Innere des Polygons in einem ellipsoidförmigen System wird von der linken Regel definiert.</span><span class="sxs-lookup"><span data-stu-id="e7567-159">The interior of the polygon in an ellipsoidal system is defined by the left-hand rule.</span></span>

 <span data-ttu-id="e7567-160">Wenn der Kompatibilitäts Grad 100 oder niedriger ist, [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] `geography` weist der Datentyp die folgenden Einschränkungen auf:</span><span class="sxs-lookup"><span data-stu-id="e7567-160">When the compatibility level is 100 or below in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] then the `geography` data type has the following restrictions:</span></span>

-   <span data-ttu-id="e7567-161">Jede `geography`-Instanz muss in genau eine Hemisphäre passen.</span><span class="sxs-lookup"><span data-stu-id="e7567-161">Each `geography` instance must fit inside a single hemisphere.</span></span> <span data-ttu-id="e7567-162">Es können keine räumlichen Objekte gespeichert werden, die größer als eine Hemisphäre sind.</span><span class="sxs-lookup"><span data-stu-id="e7567-162">No spatial objects larger than a hemisphere can be stored.</span></span>

-   <span data-ttu-id="e7567-163">Jede `geography`-Instanz aus einer Darstellung des Typs Open Geospatial Consortium (OGC) Well-Known Text (WKT) oder Well-Known Binary (WKB), die ein Objekt ergibt, das größer als eine Hemisphäre ist, löst eine Ausnahme des Typs `ArgumentException` aus.</span><span class="sxs-lookup"><span data-stu-id="e7567-163">Any `geography` instance from an Open Geospatial Consortium (OGC) Well-Known Text (WKT) or Well-Known Binary (WKB) representation that produces an object larger than a hemisphere throws an `ArgumentException`.</span></span>

-   <span data-ttu-id="e7567-164">Die `geography` Datentyp Methoden, die die Eingabe von zwei- `geography` Instanzen erfordern, wie z. b. stschnitt(), STUnion (), STDifference () und STSymDifference (), geben NULL zurück, wenn die Ergebnisse der Methoden nicht in eine einzelne Hemisphäre passen.</span><span class="sxs-lookup"><span data-stu-id="e7567-164">The `geography` data type methods that require the input of two `geography` instances, such as STIntersection(), STUnion(), STDifference(), and STSymDifference(), will return null if the results from the methods do not fit inside a single hemisphere.</span></span> <span data-ttu-id="e7567-165">STBuffer() gibt ebenfalls NULL zurück, wenn die Ausgabe eine Hemisphäre überschreitet.</span><span class="sxs-lookup"><span data-stu-id="e7567-165">STBuffer() will also return null if the output exceeds a single hemisphere.</span></span>

 <span data-ttu-id="e7567-166">In [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] ist `FullGlobe` ein spezieller Polygontyp, der den gesamten Globus abdeckt.</span><span class="sxs-lookup"><span data-stu-id="e7567-166">In [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], `FullGlobe` is a special type of Polygon that covers the entire globe.</span></span> <span data-ttu-id="e7567-167">`FullGlobe` verfügt über einen Bereich, aber nicht über Rahmen oder Scheitelpunkte.</span><span class="sxs-lookup"><span data-stu-id="e7567-167">`FullGlobe` has an area, but no borders or vertices.</span></span>

### <a name="outer-and-inner-rings-not-important-in-geography-data-type"></a><span data-ttu-id="e7567-168">Äußere und innere Ringe sind beim geography-Datentyp nicht von Bedeutung</span><span class="sxs-lookup"><span data-stu-id="e7567-168">Outer and inner rings not important in geography data type</span></span>
 <span data-ttu-id="e7567-169">In der OGC Simple Features for SQL-Spezifikation werden äußere und innere Ringe erörtert. diese Unterscheidung ist jedoch für den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `geography` Datentyp nicht sinnvoll. jeder Ring eines Polygons kann als äußerer Ring verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7567-169">The OGC Simple Features for SQL Specification discusses outer rings and inner rings, but this distinction makes little sense for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `geography` data type; any ring of a polygon can be taken to be the outer ring.</span></span>

 <span data-ttu-id="e7567-170">Weitere Informationen zu den OGC-Spezifikationen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="e7567-170">For more information on OGC specifications, see the following:</span></span>

-   [<span data-ttu-id="e7567-171">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span><span class="sxs-lookup"><span data-stu-id="e7567-171">OGC Specifications, Simple Feature Access Part 1 - Common Architecture</span></span>](https://go.microsoft.com/fwlink/?LinkId=93627)

-   [<span data-ttu-id="e7567-172">OGC Specifications, Simple Feature Access Part 2: SQL Options (OGC-Spezifikationen, Simple Feature Access, Teil 2: SQL-Optionen)</span><span class="sxs-lookup"><span data-stu-id="e7567-172">OGC Specifications, Simple Feature Access Part 2 - SQL Options</span></span>](https://go.microsoft.com/fwlink/?LinkId=93628)


##  <a name="circular-arc-segments"></a><a name="circular"></a> <span data-ttu-id="e7567-173">Kreisbogensegmente</span><span class="sxs-lookup"><span data-stu-id="e7567-173">Circular Arc Segments</span></span>
 <span data-ttu-id="e7567-174">Drei instanziierbare Typen können Kreisbogensegmente verwenden: `CircularString`, `CompoundCurve` und `CurvePolygon`.</span><span class="sxs-lookup"><span data-stu-id="e7567-174">Three instantiable types can take circular arc segments: `CircularString`, `CompoundCurve`, and `CurvePolygon`.</span></span>  <span data-ttu-id="e7567-175">Ein Kreisbogensegment wird von drei Punkten in einer zweidimensionalen Ebene definiert; der dritte Punkt darf nicht mit dem ersten Punkt identisch sein.</span><span class="sxs-lookup"><span data-stu-id="e7567-175">A circular arc segment is defined by three points in a two dimensional plane and the third point cannot be the same as the first point.</span></span>

 <span data-ttu-id="e7567-176">In Abbildung A und B sind typische Kreisbogensegmente dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e7567-176">Figures A and B show typical circular arc segments.</span></span> <span data-ttu-id="e7567-177">Beachten Sie, dass jeder der drei Punkte auf dem Umkreis eines Kreises liegt.</span><span class="sxs-lookup"><span data-stu-id="e7567-177">Note how each of the three points lie on the perimeter of a circle.</span></span>

 <span data-ttu-id="e7567-178">In Abbildung C und D ist dargestellt, wie ein Liniensegment als Kreisbogensegment definiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="e7567-178">Figures C and D show how a line segment can be defined as a circular arc segment.</span></span>  <span data-ttu-id="e7567-179">Beachten Sie, dass auch hier, im Gegensatz zu einem regulären Liniensegment, das mit nur zwei Punkten definierten werden kann, drei Punkte erforderlich sind, um das Kreisbogensegment zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e7567-179">Note that three points are still needed to define the circular arc segment unlike a regular line segment which can be defined by just two points.</span></span>

 <span data-ttu-id="e7567-180">Methoden, die für Kreisbogensegmenttypen ausgeführt werden, verwenden gerade Liniensegmente zur Annäherung an den Kreisbogen. Die Anzahl von Liniensegmenten, die zur Annäherung an den Bogen verwendet wird, ist von der Länge und der Krümmung des Bogens abhängig. Für jeden Kreisbogensegmenttyp können Z-Werte können gespeichert werden, diese werden jedoch von Methoden nicht in ihren Berechnungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="e7567-180">Methods operating on circular arc segment types use straight line segments to approximate the circular arc. The number of line segments used to approximate the arc will depend on the length and curvature of the arc. Z values can be stored for each of the circular arc segment types; however, methods will not use the Z values in their calculations.</span></span>

> [!NOTE]
>  <span data-ttu-id="e7567-181">Wenn Z-Werte für Kreisbogensegmente angegeben werden, müssen diese für alle Punkte in dem Kreisbogensegment gleich sein, damit sie als Eingabe akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="e7567-181">If Z values are given for circular arc segments then they must be the same for all points in the circular arc segment for it to be accepted for input.</span></span> <span data-ttu-id="e7567-182">Beispielsweise ist `CIRCULARSTRING(0 0 1, 2 2 1, 4 0 1)` zulässig, `CIRCULARSTRING(0 0 1, 2 2 2, 4 0 1)` jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="e7567-182">For example: `CIRCULARSTRING(0 0 1, 2 2 1, 4 0 1)` is accepted, but `CIRCULARSTRING(0 0 1, 2 2 2, 4 0 1)` is not accepted.</span></span>

### <a name="linestring-and-circularstring-comparison"></a><span data-ttu-id="e7567-183">Vergleich von LineString und CircularString</span><span class="sxs-lookup"><span data-stu-id="e7567-183">LineString and CircularString comparison</span></span>
 <span data-ttu-id="e7567-184">Im folgenden Diagramm sind identische gleichschenklige Dreiecke dargestellt (Dreieck A verwendet Liniensegmente zur Definition des Dreiecks, Dreieck B verwendet Kreisbogensegmente zur Definition des Dreiecks):</span><span class="sxs-lookup"><span data-stu-id="e7567-184">The following diagram shows identical isosceles triangles (triangle A uses line segments to define the triangle and triangle B uses circular arc segments to defined the triangle):</span></span>

 ![](../../database-engine/media/7e382f76-59da-4b62-80dc-caf93e637c14.png "7e382f76-59da-4b62-80dc-caf93e637c14")

 <span data-ttu-id="e7567-185">In diesem Beispiel wird gezeigt, wie die oben erwähnten gleichschenkligen Dreiecke mit einer `LineString`-Instanz und einer `CircularString`-Instanz gespeichert werden:</span><span class="sxs-lookup"><span data-stu-id="e7567-185">This example shows how to store the above isosceles triangles using both a `LineString` instance and `CircularString` instance:</span></span>

```sql
DECLARE @g1 geometry;
DECLARE @g2 geometry;
SET @g1 = geometry::STGeomFromText('LINESTRING(1 1, 5 1, 3 5, 1 1)', 0);
SET @g2 = geometry::STGeomFromText('CIRCULARSTRING(1 1, 3 1, 5 1, 4 3, 3 5, 2 3, 1 1)', 0);
IF @g1.STIsValid() = 1 AND @g2.STIsValid() = 1
  BEGIN
      SELECT @g1.ToString(), @g2.ToString()
      SELECT @g1.STLength() AS [LS Length], @g2.STLength() AS [CS Length]
  END
```

 <span data-ttu-id="e7567-186">Beachten Sie, dass eine `CircularString`-Instanz sieben Punkte erfordert, um das Dreieck zu definieren, eine `LineString`-Instanz erfordert jedoch nur vier Punkte, um das Dreieck zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e7567-186">Notice that a `CircularString` instance requires seven points to define the triangle, but a `LineString` instance requires only four points to define the triangle.</span></span> <span data-ttu-id="e7567-187">Der Grund hierfür ist, dass eine `CircularString`-Instanz Kreisbogensegmente und keine Liniensegmente speichert.</span><span class="sxs-lookup"><span data-stu-id="e7567-187">The reason for this is that a `CircularString` instance stores circular arc segments and not line segments.</span></span> <span data-ttu-id="e7567-188">Deshalb sind die Seiten des in der `CircularString`-Instanz gespeicherten Dreiecks ABC, CDE und EFA, wohingegen die Seiten des in der `LineString`-Instanz gespeicherten Dreiecks AC, CE und EA sind.</span><span class="sxs-lookup"><span data-stu-id="e7567-188">So the sides of the triangle stored in the `CircularString` instance are ABC, CDE, and EFA whereas the sides of the triangle stored in the `LineString` instance are AC, CE, and EA.</span></span>

 <span data-ttu-id="e7567-189">Betrachten Sie den folgenden Codeausschnitt:</span><span class="sxs-lookup"><span data-stu-id="e7567-189">Consider the following code snippet:</span></span>

```sql
SET @g1 = geometry::STGeomFromText('LINESTRING(0 0, 2 2, 4 0)', 0);
SET @g2 = geometry::STGeomFromText('CIRCULARSTRING(0 0, 2 2, 4 0)', 0);
SELECT @g1.STLength() AS [LS Length], @g2.STLength() AS [CS Length];
```

 <span data-ttu-id="e7567-190">Dieser Ausschnitt liefert die folgende Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="e7567-190">This snippet will produce the following results:</span></span>

```
LS LengthCS Length
5.65685...6.28318...
```

 <span data-ttu-id="e7567-191">Die folgende Abbildung zeigt, wie die einzelnen Typen gespeichert werden (rote Linien anzeigen `LineString``@g1` , blaue Linien anzeigen `CircularString``@g2` ):</span><span class="sxs-lookup"><span data-stu-id="e7567-191">The following illustration shows how each type is stored (red line shows `LineString``@g1`, blue line shows `CircularString``@g2`):</span></span>

 ![](../../database-engine/media/e52157b5-5160-4a4b-8560-50cdcf905b76.png "e52157b5-5160-4a4b-8560-50cdcf905b76")

 <span data-ttu-id="e7567-192">Wie die obige Abbildung zeigt, verwenden `CircularString`-Instanzen weniger Punkte, um Kurvenbegrenzungen mit größerer Genauigkeit zu speichern, als `LineString`-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="e7567-192">As the illustration above shows, `CircularString` instances use fewer points to store curve boundaries with greater precision than `LineString` instances.</span></span> <span data-ttu-id="e7567-193">`CircularString`-Instanzen sind hilfreich für das Speichern von Kreisbegrenzungen, z. B. ein Suchradius von zwanzig Kilometern von einem bestimmten Punkt aus.</span><span class="sxs-lookup"><span data-stu-id="e7567-193">`CircularString` instances are useful for storing circular boundaries like a twenty-mile search radius from a specific point.</span></span> <span data-ttu-id="e7567-194">`LineString`-Instanzen eignen sich für das Speichern von linearen Grenzen, z. B. ein Häuserblock.</span><span class="sxs-lookup"><span data-stu-id="e7567-194">`LineString` instances are good for storing boundaries that are linear like a square city block.</span></span>

### <a name="linestring-and-compoundcurve-comparison"></a><span data-ttu-id="e7567-195">Vergleich von LineString und CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="e7567-195">LineString and CompoundCurve comparison</span></span>
 <span data-ttu-id="e7567-196">In den folgenden Codebeispielen ist dargestellt, wie die gleiche Abbildung mit `LineString`- und `CompoundCurve`-Instanzen gespeichert wird:</span><span class="sxs-lookup"><span data-stu-id="e7567-196">The following code examples show how to store the same figure using `LineString` and `CompoundCurve` instances:</span></span>

```sql
SET @g = geometry::Parse('LINESTRING(2 2, 4 2, 4 4, 2 4, 2 2)');
SET @g = geometry::Parse('COMPOUNDCURVE((2 2, 4 2), (4 2, 4 4), (4 4, 2 4), (2 4, 2 2))');
SET @g = geometry::Parse('COMPOUNDCURVE((2 2, 4 2, 4 4, 2 4, 2 2))');
```

 <span data-ttu-id="e7567-197">oder</span><span class="sxs-lookup"><span data-stu-id="e7567-197">or</span></span>

 <span data-ttu-id="e7567-198">In den obigen Beispielen könnte die Abbildung entweder mit einer `LineString`-Instanz oder einer `CompoundCurve`-Instanz gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e7567-198">In the examples above, either a `LineString` instance or a `CompoundCurve` instance could store the figure.</span></span>  <span data-ttu-id="e7567-199">Im nächsten Beispiel wird ein Kreisslice mithilfe eines `CompoundCurve` gespeichert:</span><span class="sxs-lookup"><span data-stu-id="e7567-199">This next example uses a `CompoundCurve` to store a pie slice:</span></span>

```sql
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(2 2, 1 3, 0 2),(0 2, 1 0, 2 2))');
```

 <span data-ttu-id="e7567-200">Eine `CompoundCurve`-Instanz kann das Kreisbogensegment (2 2, 1 3, 0 2) direkt speichern, wohingegen eine `LineString`-Instanz die Kurve in mehrere kleinere Liniensegmente konvertieren müsste.</span><span class="sxs-lookup"><span data-stu-id="e7567-200">A `CompoundCurve` instance can store the circular arc segment (2 2, 1 3, 0 2) directly whereas a `LineString` instance would have to convert the curve into several smaller line segments.</span></span>

### <a name="circularstring-and-compoundcurve-comparison"></a><span data-ttu-id="e7567-201">Vergleich von CircularString und CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="e7567-201">CircularString and CompoundCurve comparison</span></span>
 <span data-ttu-id="e7567-202">Im folgenden Codebeispiel wird gezeigt, wie der Kreisslice in einer `CircularString`-Instanz gespeichert werden kann:</span><span class="sxs-lookup"><span data-stu-id="e7567-202">The following code example shows how the pie slice can be stored in a `CircularString` instance:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('CIRCULARSTRING( 0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0)');
SELECT @g.ToString(), @g.STLength();
```

 <span data-ttu-id="e7567-203">Zum Speichern des Kreisslices mit einer `CircularString`-Instanz müssen drei Punkte für jedes Liniensegment verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7567-203">To store the pie slice using a `CircularString` instance requires that three points be used for each line segment.</span></span>  <span data-ttu-id="e7567-204">Wenn ein Zwischenpunkt nicht bekannt wird, muss er entweder berechnet werden, oder der Endpunkt des Liniensegments muss verdoppelt werden, wie im folgenden Codeausschnitt dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e7567-204">If an intermediate point is not known, it either has to be calculated or the endpoint of the line segment has to be doubled as the following snippet shows:</span></span>

```sql
SET @g = geometry::Parse('CIRCULARSTRING( 0 0, 3 6.3246, 3 6.3246, 0 7, -3 6.3246, 0 0, 0 0)');
```

 <span data-ttu-id="e7567-205">`CompoundCurve`-Instanzen ermöglichen sowohl `LineString` die-als auch `CircularString` die-Komponente, sodass nur zwei Punkte der Liniensegmente des Kreis Slice bekannt sein müssen.</span><span class="sxs-lookup"><span data-stu-id="e7567-205">`CompoundCurve` instances allow both `LineString` and `CircularString` components so that only two points to the line segments of the pie slice need to be known.</span></span>  <span data-ttu-id="e7567-206">In diesem Codebeispiel wird gezeigt, wie ein `CompoundCurve` verwendet wird, um die gleiche Abbildung zu speichern:</span><span class="sxs-lookup"><span data-stu-id="e7567-206">This code example shows how to use a `CompoundCurve` to store the same figure:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING( 3 6.3246, 0 7, -3 6.3246), (-3 6.3246, 0 0, 3 6.3246))');
SELECT @g.ToString(), @g.STLength();
```

### <a name="polygon-and-curvepolygon-comparison"></a><span data-ttu-id="e7567-207">Vergleich von Polygon und CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="e7567-207">Polygon and CurvePolygon comparison</span></span>
 <span data-ttu-id="e7567-208">`CurvePolygon`-Instanzen können beim Definieren ihrer äußeren und inneren Ringe `CircularString`- und `CompoundCurve`-Instanzen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e7567-208">`CurvePolygon` instances can use `CircularString` and `CompoundCurve` instances when defining their exterior and interior rings.</span></span>  <span data-ttu-id="e7567-209">`Polygon`-Instanzen können keine Kreisbogensegmenttypen verwenden: `CircularString` und `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="e7567-209">`Polygon` instances cannot use the circular arc segment types: `CircularString` and `CompoundCurve`.</span></span>


## <a name="see-also"></a><span data-ttu-id="e7567-210">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e7567-210">See Also</span></span>
 <span data-ttu-id="e7567-211">[Räumliche Daten &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) [geometry-Datentyp-Methoden Verweis](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) [geography-Datentyp-Methoden Verweis](/sql/t-sql/spatial-geography/spatial-types-geography) [stnumcurves &#40;geometry-Datentyp&#41;](/sql/t-sql/spatial-geometry/stnumcurves-geometry-data-type) [stnumcurves #b4 geography-Datentyp&#41;](/sql/t-sql/spatial-geography/stnumcurves-geography-data-type) [STGeomFromText &#40;Geometry](/sql/t-sql/spatial-geometry/stgeomfromtext-geometry-data-type) -Datentyp&#41;[STGeomFromText &#40;geography](/sql/t-sql/spatial-geography/stgeomfromtext-geography-data-type) -Datentyp&#41;</span><span class="sxs-lookup"><span data-stu-id="e7567-211">[Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) [geometry Data Type Method Reference](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) [geography Data Type Method Reference](/sql/t-sql/spatial-geography/spatial-types-geography) [STNumCurves &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnumcurves-geometry-data-type) [STNumCurves &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stnumcurves-geography-data-type) [STGeomFromText &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stgeomfromtext-geometry-data-type) [STGeomFromText &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stgeomfromtext-geography-data-type)</span></span>


