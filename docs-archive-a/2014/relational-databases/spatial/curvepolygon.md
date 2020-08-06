---
title: CurvePolygon | Microsoft-Dokumentation
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: e000a1d8-a049-4542-bfeb-943fd6ab3969
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: b90fdbd9a0bc80dfc6a82416d0193b2951fe13ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609058"
---
# <a name="curvepolygon"></a><span data-ttu-id="1a033-102">CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="1a033-102">CurvePolygon</span></span>
  <span data-ttu-id="1a033-103">Ein `CurvePolygon` ist eine von einem äußeren Begrenzungsring und null oder mehr inneren Ringe definierte topologisch geschlossene Fläche.</span><span class="sxs-lookup"><span data-stu-id="1a033-103">A `CurvePolygon` is a topologically closed surface defined by an exterior bounding ring and zero or more interior rings</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1a033-104">Laden Sie für eine ausführliche Beschreibung und Beispiele der in eingeführten räumlichen Funktionen [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , einschließlich des `CurvePolygon` unter Typs, das Whitepaper [neue räumliche Funktionen in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407)herunter.</span><span class="sxs-lookup"><span data-stu-id="1a033-104">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including the `CurvePolygon` subtype, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>  
  
 <span data-ttu-id="1a033-105">Die folgenden Kriterien definieren die Attribute einer- `CurvePolygon` Instanz:</span><span class="sxs-lookup"><span data-stu-id="1a033-105">The following criteria define attributes of a `CurvePolygon` instance:</span></span>  
  
-   <span data-ttu-id="1a033-106">Die Begrenzung der `CurvePolygon`-Instanz wird durch den äußeren Ring und alle inneren Ringe definiert.</span><span class="sxs-lookup"><span data-stu-id="1a033-106">The boundary of the `CurvePolygon` instance is defined by the exterior ring and all interior rings.</span></span>  
  
-   <span data-ttu-id="1a033-107">Das Innere der `CurvePolygon`-Instanz ist die Fläche zwischen dem äußeren Ring und allen inneren Ringen.</span><span class="sxs-lookup"><span data-stu-id="1a033-107">The interior of the `CurvePolygon` instance is the space between the exterior ring and all of the interior rings.</span></span>  
  
 <span data-ttu-id="1a033-108">Eine `CurvePolygon`-Instanz unterscheidet sich von einer `Polygon`-Instanz darin, dass eine `CurvePolygon`-Instanz die folgenden Kreisbogensegmente enthalten kann: `CircularString` und `CompoundCurve`.</span><span class="sxs-lookup"><span data-stu-id="1a033-108">A `CurvePolygon` instance differs from a `Polygon` instance in that a `CurvePolygon` instance may contain the following circular arc segments: `CircularString` and `CompoundCurve`.</span></span>  
  
## <a name="compoundcurve-instances"></a><span data-ttu-id="1a033-109">CompoundCurve-Instanzen</span><span class="sxs-lookup"><span data-stu-id="1a033-109">CompoundCurve instances</span></span>  
 <span data-ttu-id="1a033-110">In der unten stehenden Abbildung werden gültige `CurvePolygon`-Instanzen dargestellt:</span><span class="sxs-lookup"><span data-stu-id="1a033-110">Illustration below shows valid `CurvePolygon` figures:</span></span>  
  
### <a name="accepted-instances"></a><span data-ttu-id="1a033-111">Akzeptierte Instanzen</span><span class="sxs-lookup"><span data-stu-id="1a033-111">Accepted instances</span></span>  
 <span data-ttu-id="1a033-112">Damit eine `CurvePolygon`-Instanz akzeptiert wird, muss sie entweder leer sein oder ausschließlich akzeptierte Kreisbogenringe enthalten.</span><span class="sxs-lookup"><span data-stu-id="1a033-112">For a `CurvePolygon` instance to be accepted, it needs to be either empty or contain only circular arc rings that are accepted.</span></span> <span data-ttu-id="1a033-113">Ein akzeptierter Kreisbogenring erfüllt die folgenden Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="1a033-113">An accepted circular arc ring meets the following requirements.</span></span>  
  
1.  <span data-ttu-id="1a033-114">Er stellt eine akzeptierte `LineString`-, `CircularString`- oder `CompoundCurve`-Instanz dar.</span><span class="sxs-lookup"><span data-stu-id="1a033-114">Is an accepted `LineString`, `CircularString`, or `CompoundCurve` instance.</span></span> <span data-ttu-id="1a033-115">Weitere Informationen zu akzeptierten Instanzen finden Sie unter [LineString](linestring.md), [CircularString](circularstring.md)und [CompoundCurve](compoundcurve.md).</span><span class="sxs-lookup"><span data-stu-id="1a033-115">For more information on accepted instances, see [LineString](linestring.md), [CircularString](circularstring.md), and [CompoundCurve](compoundcurve.md).</span></span>  
  
2.  <span data-ttu-id="1a033-116">Er enthält mindestens vier Punkte.</span><span class="sxs-lookup"><span data-stu-id="1a033-116">Has at least four points.</span></span>  
  
3.  <span data-ttu-id="1a033-117">Die X- und Y-Koordinaten für den Ausgangspunkt und den Endpunkt sind identisch.</span><span class="sxs-lookup"><span data-stu-id="1a033-117">The start and end point have the same X and Y coordinates.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1a033-118">Z- und M-Werte werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1a033-118">Z and M values are ignored.</span></span>  
  
 <span data-ttu-id="1a033-119">Im folgenden Beispiel werden akzeptierte `CurvePolygon`-Instanzen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1a033-119">The following example shows accepted `CurvePolygon` instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'CURVEPOLYGON EMPTY';  
DECLARE @g2 geometry = 'CURVEPOLYGON((0 0, 0 0, 0 0, 0 0))';  
DECLARE @g3 geometry = 'CURVEPOLYGON((0 0 1, 0 0 2, 0 0 3, 0 0 3))'  
DECLARE @g4 geometry = 'CURVEPOLYGON(CIRCULARSTRING(1 3, 3 5, 4 7, 7 3, 1 3))';  
DECLARE @g5 geography = 'CURVEPOLYGON((-122.3 47, 122.3 -47, 125.7 -49, 121 -38, -122.3 47))';  
```  
  
 <span data-ttu-id="1a033-120">`@g3` wird akzeptiert, obwohl sich die Z-Werte des Ausgangspunkts und des Endpunkts voneinander unterscheiden, da Z-Werte ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="1a033-120">`@g3` is accepted even though the start and end points have different Z values because Z values are ignored.</span></span> <span data-ttu-id="1a033-121">`@g5` wird akzeptiert, obwohl die `geography`-Typinstanz ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="1a033-121">`@g5` is accepted even though the `geography` type instance is not valid.</span></span>  
  
 <span data-ttu-id="1a033-122">In den folgenden Beispielen wird `System.FormatException`ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1a033-122">The following examples throw `System.FormatException`.</span></span>  
  
```  
DECLARE @g1 geometry = 'CURVEPOLYGON((0 5, 0 0, 0 0, 0 0))';  
DECLARE @g2 geometry = 'CURVEPOLYGON((0 0, 0 0, 0 0))';  
```  
  
 <span data-ttu-id="1a033-123">`@g1` wird nicht akzeptiert, da der Ausgangspunkt und der Endpunkt nicht denselben Y-Wert aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1a033-123">`@g1` is not accepted because the start and end points do not have the same Y value.</span></span> <span data-ttu-id="1a033-124">`@g2` wird nicht akzeptiert, da der Ring nicht über eine ausreichende Anzahl von Punkten verfügt.</span><span class="sxs-lookup"><span data-stu-id="1a033-124">`@g2` is not accepted because the ring does not have enough points.</span></span>  
  
### <a name="valid-instances"></a><span data-ttu-id="1a033-125">Gültige Instanzen</span><span class="sxs-lookup"><span data-stu-id="1a033-125">Valid instances</span></span>  
 <span data-ttu-id="1a033-126">Eine `CurvePolygon`-Instanz ist gültig, wenn sowohl der äußere Ring als auch die inneren Ringe die folgenden Kriterien erfüllen:</span><span class="sxs-lookup"><span data-stu-id="1a033-126">For a `CurvePolygon` instance to be valid both exterior and interior rings must meet the following criteria:</span></span>  
  
1.  <span data-ttu-id="1a033-127">Sie können sich nur an jeweils einem Tangentenpunkt berühren.</span><span class="sxs-lookup"><span data-stu-id="1a033-127">They may only touch at single tangent points.</span></span>  
  
2.  <span data-ttu-id="1a033-128">Sie können einander nicht schneiden.</span><span class="sxs-lookup"><span data-stu-id="1a033-128">They cannot cross each other.</span></span>  
  
3.  <span data-ttu-id="1a033-129">Jeder Ring muss mindestens vier Punkte enthalten.</span><span class="sxs-lookup"><span data-stu-id="1a033-129">Each ring must contain at least four points.</span></span>  
  
4.  <span data-ttu-id="1a033-130">Jeder Ring muss ein akzeptabler Kurventyp sein.</span><span class="sxs-lookup"><span data-stu-id="1a033-130">Each ring must be an acceptable curve type.</span></span>  
  
 <span data-ttu-id="1a033-131">Auch `CurvePolygon`-Instanzen müssen bestimmte Kriterien erfüllen, je nachdem, ob es sich dabei um einen `geometry`-Datentyp oder einen `geography`-Datentyp handelt.</span><span class="sxs-lookup"><span data-stu-id="1a033-131">`CurvePolygon` instances also need to meet specific criteria depending on whether they are `geometry` or `geography` data types.</span></span>  
  
#### <a name="geometry-data-type"></a><span data-ttu-id="1a033-132">geometry-Datentyp</span><span class="sxs-lookup"><span data-stu-id="1a033-132">Geometry data type</span></span>  
 <span data-ttu-id="1a033-133">Eine gültige **geometryCurvePolygon** -Instanz muss über die folgenden Attribute verfügen:</span><span class="sxs-lookup"><span data-stu-id="1a033-133">A valid **geometryCurvePolygon** instance must have the following attributes:</span></span>  
  
1.  <span data-ttu-id="1a033-134">Alle inneren Ringe müssen im äußeren Ring enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="1a033-134">All the interior rings must be contained within the exterior ring.</span></span>  
  
2.  <span data-ttu-id="1a033-135">Mehrere innere Ringe können vorhanden sein, ein innerer Ring darf jedoch keinen anderen inneren Ring enthalten.</span><span class="sxs-lookup"><span data-stu-id="1a033-135">May have multiple interior rings, but an interior ring cannot contain another interior ring.</span></span>  
  
3.  <span data-ttu-id="1a033-136">Ringe dürfen weder sich selbst noch einen anderen Ring schneiden.</span><span class="sxs-lookup"><span data-stu-id="1a033-136">No ring can cross itself or another ring.</span></span>  
  
4.  <span data-ttu-id="1a033-137">Ringe dürfen sich nur an einzelnen Tangentenpunkten berühren (wobei die Anzahl der Punkte, an denen Ringe einander berühren, endlich sein muss).</span><span class="sxs-lookup"><span data-stu-id="1a033-137">Rings can only touch at single tangent points (number of points where rings touch must be finite).</span></span>  
  
5.  <span data-ttu-id="1a033-138">Der Innere des Polygons muss verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="1a033-138">The interior of the polygon must be connected.</span></span>  
  
 <span data-ttu-id="1a033-139">Im folgenden Beispiel werden gültige **geometryCurvePolygon** -Instanzen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1a033-139">The following example shows valid **geometryCurvePolygon** instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'CURVEPOLYGON EMPTY';  
DECLARE @g2 geometry = 'CURVEPOLYGON(CIRCULARSTRING(1 3, 3 5, 4 7, 7 3, 1 3))';  
SELECT @g1.STIsValid(), @g2.STIsValid();  
```  
  
 <span data-ttu-id="1a033-140">Für CurvePolygon-Instanzen gelten dieselben Gültigkeitsregeln wie für Polygon-Instanzen. CurvePolygon-Instanzen können jedoch die neuen Kreisbogensegment-Typen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="1a033-140">CurvePolygon instances have the same validity rules as Polygon instances with the exception that CurvePolygon instances may accept the new circular arc segment types.</span></span> <span data-ttu-id="1a033-141">Weitere Beispiele für gültige oder nicht gültige Instanzen finden Sie unter [Polygon](polygon.md).</span><span class="sxs-lookup"><span data-stu-id="1a033-141">For more examples of instances that are valid or not valid, see [Polygon](polygon.md).</span></span>  
  
#### <a name="geography-data-type"></a><span data-ttu-id="1a033-142">geography-Datentyp</span><span class="sxs-lookup"><span data-stu-id="1a033-142">Geography data type</span></span>  
 <span data-ttu-id="1a033-143">Eine gültige **geographyCurvePolygon** -Instanz muss über die folgenden Attribute verfügen:</span><span class="sxs-lookup"><span data-stu-id="1a033-143">A valid **geographyCurvePolygon** instance must have the following attributes:</span></span>  
  
1.  <span data-ttu-id="1a033-144">Der Innere des Polygons ist mit der linken Regel verbunden.</span><span class="sxs-lookup"><span data-stu-id="1a033-144">The interior of the polygon is connected using the left-hand rule.</span></span>  
  
2.  <span data-ttu-id="1a033-145">Ringe dürfen weder sich selbst noch einen anderen Ring schneiden.</span><span class="sxs-lookup"><span data-stu-id="1a033-145">No ring can cross itself or another ring.</span></span>  
  
3.  <span data-ttu-id="1a033-146">Ringe dürfen sich nur an einzelnen Tangentenpunkten berühren (wobei die Anzahl der Punkte, an denen Ringe einander berühren, endlich sein muss).</span><span class="sxs-lookup"><span data-stu-id="1a033-146">Rings can only touch at single tangent points (number of points where rings touch must be finite).</span></span>  
  
4.  <span data-ttu-id="1a033-147">Der Innere des Polygons muss verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="1a033-147">The interior of the polygon must be connected.</span></span>  
  
 <span data-ttu-id="1a033-148">Im folgenden Beispiel wird eine gültige CurvePolygon-geography-Instanz veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="1a033-148">The following example shows a valid geography CurvePolygon instance.</span></span>  
  
```  
DECLARE @g geography = 'CURVEPOLYGON((-122.3 47, 122.3 47, 125.7 49, 121 38, -122.3 47))';  
SELECT @g.STIsValid();  
```  
  
## <a name="examples"></a><span data-ttu-id="1a033-149">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1a033-149">Examples</span></span>  
  
### <a name="a-instantiating-a-geometry-instance-with-an-empty-curvepolygon"></a><span data-ttu-id="1a033-150">A.</span><span class="sxs-lookup"><span data-stu-id="1a033-150">A.</span></span> <span data-ttu-id="1a033-151">Instanziieren einer geometry-Instanz mit einem leeren CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="1a033-151">Instantiating a Geometry Instance with an Empty CurvePolygon</span></span>  
 <span data-ttu-id="1a033-152">In diesem Beispiel wird veranschaulicht, wie eine leere `CurvePolygon`-Instanz erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="1a033-152">This example shows how to create an empty `CurvePolygon` instance:</span></span>  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CURVEPOLYGON EMPTY');  
```  
  
### <a name="b-declaring-and-instantiating-a-geometry-instance-with-a-curvepolygon-in-the-same-statement"></a><span data-ttu-id="1a033-153">B.</span><span class="sxs-lookup"><span data-stu-id="1a033-153">B.</span></span> <span data-ttu-id="1a033-154">Deklarieren und Instanziieren einer geometry-Instanz mit einem CurvePolygon in derselben Anweisung</span><span class="sxs-lookup"><span data-stu-id="1a033-154">Declaring and Instantiating a Geometry Instance with a CurvePolygon in the Same Statement</span></span>  
 <span data-ttu-id="1a033-155">In diesem Codeausschnitt wird veranschaulicht, wie eine geometry-Instanz und ein `CurvePolygon` in derselben Anweisung deklariert und initialisiert werden:</span><span class="sxs-lookup"><span data-stu-id="1a033-155">This code snippet shows how to declare and initialize a geometry instance with a `CurvePolygon` in the same statement:</span></span>  
  
```sql  
DECLARE @g geometry = 'CURVEPOLYGON(CIRCULARSTRING(2 4, 4 2, 6 4, 4 6, 2 4))'  
```  
  
### <a name="c-instantiating-a-geography-instance-with-a-curvepolygon"></a><span data-ttu-id="1a033-156">C.</span><span class="sxs-lookup"><span data-stu-id="1a033-156">C.</span></span> <span data-ttu-id="1a033-157">Instanziieren einer geography-Instanz mit einem CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="1a033-157">Instantiating a Geography Instance with a CurvePolygon</span></span>  
 <span data-ttu-id="1a033-158">In diesem Codeausschnitt wird veranschaulicht, wie eine `geography`-Instanz mit einem `CurvePolygon` deklariert und initialisiert wird:</span><span class="sxs-lookup"><span data-stu-id="1a033-158">This code snippet shows how to declare and initialize a `geography` instance with a `CurvePolygon`:</span></span>  
  
```sql  
DECLARE @g geography = 'CURVEPOLYGON(CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))';  
```  
  
### <a name="d-storing-a-curvepolygon-with-only-an-exterior-bounding-ring"></a><span data-ttu-id="1a033-159">D:</span><span class="sxs-lookup"><span data-stu-id="1a033-159">D.</span></span> <span data-ttu-id="1a033-160">Speichern eines CurvePolygon mit nur einem äußeren Begrenzungsring</span><span class="sxs-lookup"><span data-stu-id="1a033-160">Storing a CurvePolygon with Only an Exterior Bounding Ring</span></span>  
 <span data-ttu-id="1a033-161">In diesem Beispiel wird veranschaulicht, wie ein einfacher Kreis in einer `CurvePolygon`-Instanz gespeichert wird (wobei der Kreis lediglich durch einen äußeren Begrenzungsring definiert wird):</span><span class="sxs-lookup"><span data-stu-id="1a033-161">This example shows how to store a simple circle in a `CurvePolygon` instance (only an exterior bounding ring is used to define the circle):</span></span>  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(2 4, 4 2, 6 4, 4 6, 2 4))');  
SELECT @g.STArea() AS Area;  
```  
  
### <a name="e-storing-a-curvepolygon-containing-interior-rings"></a><span data-ttu-id="1a033-162">E.</span><span class="sxs-lookup"><span data-stu-id="1a033-162">E.</span></span> <span data-ttu-id="1a033-163">Speichern eines CurvePolygon mit inneren Ringen</span><span class="sxs-lookup"><span data-stu-id="1a033-163">Storing a CurvePolygon Containing Interior Rings</span></span>  
 <span data-ttu-id="1a033-164">In diesem Beispiel wird ein Rad in einer `CurvePolygon`-Instanz erstellt (das Rad wird durch einen äußeren Begrenzungsring und einen inneren Ring definiert):</span><span class="sxs-lookup"><span data-stu-id="1a033-164">This example creates a donut in a `CurvePolygon` instance (both an exterior bounding ring and an interior ring is used to define the donut):</span></span>  
  
```sql  
DECLARE @g geometry;  
SET @g = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 4, 4 0, 8 4, 4 8, 0 4), CIRCULARSTRING(2 4, 4 2, 6 4, 4 6, 2 4))');  
SELECT @g.STArea() AS Area;  
```  
  
 <span data-ttu-id="1a033-165">In diesem Beispiel werden eine gültige `CurvePolygon`-Instanz und eine ungültige Instanz für die Verwendung von inneren Ringen veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1a033-165">This example shows both a valid `CurvePolygon` instance and an invalid instance when using interior rings:</span></span>  
  
```sql  
DECLARE @g1 geometry, @g2 geometry;  
SET @g1 = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 5, 5 0, 0 -5, -5 0, 0 5), (-2 2, 2 2, 2 -2, -2 -2, -2 2))');  
IF @g1.STIsValid() = 1  
  BEGIN  
     SELECT @g1.STArea();  
  END  
SET @g2 = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 5, 5 0, 0 -5, -5 0, 0 5), (0 5, 5 0, 0 -5, -5 0, 0 5))');  
IF @g2.STIsValid() = 1  
  BEGIN  
     SELECT @g2.STArea();  
  END  
SELECT @g1.STIsValid() AS G1, @g2.STIsValid() AS G2;  
```  
  
 <span data-ttu-id="1a033-166">Sowohl @g1 als auch @g2 verwenden denselben äußeren Begrenzungsring (einen Kreis mit dem Radius 5), und für beide wird ein Quadrat als innerer Ring verwendet.</span><span class="sxs-lookup"><span data-stu-id="1a033-166">Both @g1 and @g2 use the same exterior bounding ring: a circle with a radius of 5 and they both use a square for an interior ring.</span></span>  <span data-ttu-id="1a033-167">Die Instanz @g1 ist jedoch gültig, während die Instanz @g2 ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="1a033-167">However, the instance @g1 is valid, but the instance @g2 is invalid.</span></span>  <span data-ttu-id="1a033-168">Der Grund für die Ungültigkeit von @g2 ist, dass der innere Ring die vom äußeren Ring begrenzte Fläche in vier separate Bereiche teilt.</span><span class="sxs-lookup"><span data-stu-id="1a033-168">The reason that @g2 is invalid is that the interior ring splits the interior space bounded by the exterior ring into four separate regions.</span></span>  <span data-ttu-id="1a033-169">Dies wird in der folgenden Zeichnung verdeutlicht:</span><span class="sxs-lookup"><span data-stu-id="1a033-169">The following drawing shows what occurred:</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a033-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a033-170">See Also</span></span>  
 <span data-ttu-id="1a033-171">[Polygon](polygon.md) </span><span class="sxs-lookup"><span data-stu-id="1a033-171">[Polygon](polygon.md) </span></span>  
 <span data-ttu-id="1a033-172">[CircularString](circularstring.md) </span><span class="sxs-lookup"><span data-stu-id="1a033-172">[CircularString](circularstring.md) </span></span>  
 <span data-ttu-id="1a033-173">[CompoundCurve](compoundcurve.md) </span><span class="sxs-lookup"><span data-stu-id="1a033-173">[CompoundCurve](compoundcurve.md) </span></span>  
 <span data-ttu-id="1a033-174">[geometry-Datentyp-Methodenverweis](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1a033-174">[geometry Data Type Method Reference](/sql/t-sql/spatial-geometry/spatial-types-geometry-transact-sql) </span></span>  
 <span data-ttu-id="1a033-175">[geography-Datentyp-Methodenverweis](/sql/t-sql/spatial-geography/spatial-types-geography) </span><span class="sxs-lookup"><span data-stu-id="1a033-175">[geography Data Type Method Reference](/sql/t-sql/spatial-geography/spatial-types-geography) </span></span>  
 [<span data-ttu-id="1a033-176">Übersicht über räumliche Datentypen</span><span class="sxs-lookup"><span data-stu-id="1a033-176">Spatial Data Types Overview</span></span>](spatial-data-types-overview.md)  
  
  
