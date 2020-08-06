---
title: CircularString | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: 9fe06b03-d98c-4337-9f89-54da98f49f9f
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: c701cdc2e8538a5b91093e17714fd9f6508d1c4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609065"
---
# <a name="circularstring"></a><span data-ttu-id="9a009-102">CircularString</span><span class="sxs-lookup"><span data-stu-id="9a009-102">CircularString</span></span>
  <span data-ttu-id="9a009-103">Ein `CircularString` ist eine Auflistung von 0 (null) oder mehr stetigen Kreisbogensegmenten.</span><span class="sxs-lookup"><span data-stu-id="9a009-103">A `CircularString` is a collection of zero or more continuous circular arc segments.</span></span> <span data-ttu-id="9a009-104">Ein Kreisbogensegment ist ein von drei Punkten in einer zweidimensionalen Ebene definierter gekrümmter Abschnitt; der erste Punkt darf nicht mit dem dritten Punkt identisch sein.</span><span class="sxs-lookup"><span data-stu-id="9a009-104">A circular arc segment is a curved segment defined by three points in a two-dimensional plane; the first point cannot be the same as the third point.</span></span> <span data-ttu-id="9a009-105">Wenn alle drei Punkte eines Kreisbogensegments kollinear sind, wird das Bogensegment als Liniensegment behandelt.</span><span class="sxs-lookup"><span data-stu-id="9a009-105">If all three points of a circular arc segment are collinear, the arc segment is treated as a line segment.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="9a009-106">Laden Sie für eine ausführliche Beschreibung und Beispiele der neuen räumlichen Funktionen in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , einschließlich des `CircularString` unter Typs, das Whitepaper [neue räumliche Funktionen in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407)herunter.</span><span class="sxs-lookup"><span data-stu-id="9a009-106">For a detailed description and examples of the new spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including the `CircularString` subtype, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>

## <a name="circularstring-instances"></a><span data-ttu-id="9a009-107">CircularString-Instanzen</span><span class="sxs-lookup"><span data-stu-id="9a009-107">CircularString instances</span></span>
 <span data-ttu-id="9a009-108">In der unten stehenden Zeichnung sind gültige `CircularString`-Instanzen dargestellt:</span><span class="sxs-lookup"><span data-stu-id="9a009-108">The drawing below shows valid `CircularString` instances:</span></span>

 ![](../../database-engine/media/5ff17e34-b578-4873-9d33-79500940d0bc.png "5ff17e34-b578-4873-9d33-79500940d0bc")

### <a name="accepted-instances"></a><span data-ttu-id="9a009-109">Akzeptierte Instanzen</span><span class="sxs-lookup"><span data-stu-id="9a009-109">Accepted instances</span></span>
 <span data-ttu-id="9a009-110">Eine- `CircularString` Instanz wird akzeptiert, wenn Sie entweder leer ist oder eine ungerade Anzahl von Punkten enthält, n, wobei n > 1 ist.</span><span class="sxs-lookup"><span data-stu-id="9a009-110">A `CircularString` instance is accepted if it is either empty or contains an odd number of points, n, where n > 1.</span></span> <span data-ttu-id="9a009-111">Die folgenden `CircularString`-Instanzen werden akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="9a009-111">The following `CircularString` instances are accepted.</span></span>

```sql
DECLARE @g1 geometry = 'CIRCULARSTRING EMPTY';
DECLARE @g2 geometry = 'CIRCULARSTRING(1 1, 2 0, -1 1)';
DECLARE @g3 geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 2 0, 1 1)';
```

 <span data-ttu-id="9a009-112">`@g3` zeigt, dass eine `CircularString`-Instanz akzeptiert werden kann, jedoch nicht gültig ist.</span><span class="sxs-lookup"><span data-stu-id="9a009-112">`@g3` shows that `CircularString` instance may be accepted, but not valid.</span></span> <span data-ttu-id="9a009-113">Die folgende Deklaration einer CircularString-Instanz wird nicht akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="9a009-113">The following CircularString instance declaration is not accepted.</span></span> <span data-ttu-id="9a009-114">Diese Deklaration löst eine `System.FormatException`aus.</span><span class="sxs-lookup"><span data-stu-id="9a009-114">This declaration throws a `System.FormatException`.</span></span>

```sql
DECLARE @g geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 1 1)';
```

### <a name="valid-instances"></a><span data-ttu-id="9a009-115">Gültige Instanzen</span><span class="sxs-lookup"><span data-stu-id="9a009-115">Valid instances</span></span>
 <span data-ttu-id="9a009-116">Eine gültige `CircularString`-Instanz muss leer sein oder über die folgenden Attribute verfügen:</span><span class="sxs-lookup"><span data-stu-id="9a009-116">A valid `CircularString` instance must be empty or have the following attributes:</span></span>

-   <span data-ttu-id="9a009-117">Sie muss mindestens ein Kreisbogensegment enthalten (d. h., sie muss mindestens über drei Punkte verfügen).</span><span class="sxs-lookup"><span data-stu-id="9a009-117">It must contain at least one circular arc segment (that is, have a minimum of three points).</span></span>

-   <span data-ttu-id="9a009-118">Der letzte Endpunkt für jedes Kreisbogensegment in der Sequenz (mit Ausnahme des letzten Segments) muss dem ersten Endpunkt für das jeweils nächste Segment in der Sequenz entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9a009-118">The last endpoint for each circular arc segment in the sequence, except for the last segment, must be the first endpoint for the next segment in the sequence.</span></span>

-   <span data-ttu-id="9a009-119">Sie muss eine ungerade Anzahl von Punkten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="9a009-119">It must have an odd number of points.</span></span>

-   <span data-ttu-id="9a009-120">Sie darf sich über ein Intervalls nicht selbst überlappen.</span><span class="sxs-lookup"><span data-stu-id="9a009-120">It cannot overlap itself over an interval.</span></span>

-   <span data-ttu-id="9a009-121">`CircularString`-Instanzen können zwar Liniensegmente enthalten, diese Liniensegmente müssen jedoch durch drei kollineare Punkte definiert werden.</span><span class="sxs-lookup"><span data-stu-id="9a009-121">Although `CircularString` instances may contain line segments, these line segments must be defined by three collinear points.</span></span>

 <span data-ttu-id="9a009-122">Im folgenden Beispiel werden gültige `CircularString`-Instanzen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9a009-122">The following example shows valid `CircularString` instances.</span></span>

```sql
DECLARE @g1 geometry = 'CIRCULARSTRING EMPTY';
DECLARE @g2 geometry = 'CIRCULARSTRING(1 1, 2 0, -1 1)';
DECLARE @g3 geometry = 'CIRCULARSTRING(1 1, 2 0, 2 0, 1 1, 0 1)';
DECLARE @g4 geometry = 'CIRCULARSTRING(1 1, 2 2, 2 2)';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(),@g4.STIsValid();
```

 <span data-ttu-id="9a009-123">Eine `CircularString`-Instanz muss mindestens zwei Kreisbogensegmente enthalten, damit ein vollständiger Kreis definiert wird.</span><span class="sxs-lookup"><span data-stu-id="9a009-123">A `CircularString` instance must contain at least two circular arc segments to define a complete circle.</span></span> <span data-ttu-id="9a009-124">In einer `CircularString`-Instanz kann kein einzelnes Kreisbogensegment (z. B. 1 1, 3 1, 1 1) verwendet werden, um einen vollständigen Kreis zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9a009-124">A `CircularString` instance cannot use a single circular arc segment (such as (1 1, 3 1, 1 1)) to define a complete circle.</span></span> <span data-ttu-id="9a009-125">Definieren Sie den Kreis mit (1 1, 2 2, 3 1, 2 0, 1 1).</span><span class="sxs-lookup"><span data-stu-id="9a009-125">Use (1 1, 2 2, 3 1, 2 0, 1 1) to define the circle.</span></span>

 <span data-ttu-id="9a009-126">Im folgenden Beispiel werden CircularString-Instanzen veranschaulicht, die nicht gültig sind.</span><span class="sxs-lookup"><span data-stu-id="9a009-126">The following example shows CircularString instances that are not valid.</span></span>

```sql
DECLARE @g1 geometry = 'CIRCULARSTRING(1 1, 2 0, 1 1)';
DECLARE @g2 geometry = 'CIRCULARSTRING(0 0, 0 0, 0 0)';
SELECT @g1.STIsValid(), @g2.STIsValid();
```

### <a name="instances-with-collinear-points"></a><span data-ttu-id="9a009-127">Instanzen mit kollinearen Punkten</span><span class="sxs-lookup"><span data-stu-id="9a009-127">Instances with collinear points</span></span>
 <span data-ttu-id="9a009-128">In den folgenden Fällen wird ein Kreisbogensegment als Liniensegment behandelt:</span><span class="sxs-lookup"><span data-stu-id="9a009-128">In the following cases a circular arc segment will be treated as a line segment:</span></span>

-   <span data-ttu-id="9a009-129">Wenn alle drei Punkte kollinear (z. B. 1 3, 4 4, 7 5) sind.</span><span class="sxs-lookup"><span data-stu-id="9a009-129">When all three points are collinear (for example, (1 3, 4 4, 7 5)).</span></span>

-   <span data-ttu-id="9a009-130">Wenn der erste und der mittlere Punkt identisch sind und sich beide vom dritten Punkt unterscheiden (z. B. 1 3, 1 3, 7 5).</span><span class="sxs-lookup"><span data-stu-id="9a009-130">When the first and middle point are the same, but the third point is different (for example, (1 3, 1 3, 7 5)).</span></span>

-   <span data-ttu-id="9a009-131">Wenn der mittlere und der letzte Punkt identisch sind und sich beide vom ersten Punkt unterscheiden (z. B. 1 3, 4 4, 4 4).</span><span class="sxs-lookup"><span data-stu-id="9a009-131">When the middle and last point are the same, but the first point is different (for example, (1 3, 4 4, 4 4)).</span></span>

## <a name="examples"></a><span data-ttu-id="9a009-132">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9a009-132">Examples</span></span>

### <a name="a-instantiating-a-geometry-instance-with-an-empty-circularstring"></a><span data-ttu-id="9a009-133">A.</span><span class="sxs-lookup"><span data-stu-id="9a009-133">A.</span></span> <span data-ttu-id="9a009-134">Instanziieren einer Geometry-Instanz mit einem leeren CircularString</span><span class="sxs-lookup"><span data-stu-id="9a009-134">Instantiating a Geometry Instance with an Empty CircularString</span></span>
 <span data-ttu-id="9a009-135">In diesem Beispiel wird veranschaulicht, wie eine leere `CircularString`-Instanz erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="9a009-135">This example shows how to create an empty `CircularString` instance:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('CIRCULARSTRING EMPTY');
```

### <a name="b-instantiating-a-geometry-instance-using-a-circularstring-with-one-circular-arc-segment"></a><span data-ttu-id="9a009-136">B.</span><span class="sxs-lookup"><span data-stu-id="9a009-136">B.</span></span> <span data-ttu-id="9a009-137">Instanziieren einer Geometry-Instanz, die einen CircularString mit einem Kreisbogensegment verwendet</span><span class="sxs-lookup"><span data-stu-id="9a009-137">Instantiating a Geometry Instance Using a CircularString with One Circular Arc Segment</span></span>
 <span data-ttu-id="9a009-138">Im folgenden Beispiel wird veranschaulicht, wie eine `CircularString`-Instanz mit einem einzelnen Kreisbogensegment (Halbkreis) erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="9a009-138">The following example shows how to create a `CircularString` instance with a single circular arc segment (half-circle):</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry:: STGeomFromText('CIRCULARSTRING(2 0, 1 1, 0 0)', 0);
SELECT @g.ToString();
```

### <a name="c-instantiating-a-geometry-instance-using-a-circularstring-with-multiple-circular-arc-segments"></a><span data-ttu-id="9a009-139">C.</span><span class="sxs-lookup"><span data-stu-id="9a009-139">C.</span></span> <span data-ttu-id="9a009-140">Instanziieren einer Geometry-Instanz, die einen CircularString mit mehreren Kreisbogensegmenten verwendet</span><span class="sxs-lookup"><span data-stu-id="9a009-140">Instantiating a Geometry Instance Using a CircularString with Multiple Circular Arc Segments</span></span>
 <span data-ttu-id="9a009-141">Im folgenden Beispiel wird veranschaulicht, wie eine `CircularString`-Instanz mit mehreren Kreisbogensegmenten (vollständiger Kreis) erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="9a009-141">The following example shows how to create a `CircularString` instance with more than one circular arc segment (full circle):</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('CIRCULARSTRING(2 1, 1 2, 0 1, 1 0, 2 1)');
SELECT 'Circumference = ' + CAST(@g.STLength() AS NVARCHAR(10));  
```

 <span data-ttu-id="9a009-142">Dies erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="9a009-142">This produces the following output:</span></span>

```
Circumference = 6.28319
```

 <span data-ttu-id="9a009-143">Vergleichen Sie die Ausgabe, wenn `LineString` anstelle von `CircularString` verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="9a009-143">Compare the output when `LineString` is used instead of `CircularString`:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('LINESTRING(2 1, 1 2, 0 1, 1 0, 2 1)', 0);
SELECT 'Perimeter = ' + CAST(@g.STLength() AS NVARCHAR(10));
```

 <span data-ttu-id="9a009-144">Dies erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="9a009-144">This produces the following output:</span></span>

```
Perimeter = 5.65685
```

 <span data-ttu-id="9a009-145">Beachten Sie, dass der Wert für das `CircularString` Beispiel nahe bei 2&#x03c0; (2 \* PI) liegt. Dies ist der tatsächliche Umfang des Kreises.</span><span class="sxs-lookup"><span data-stu-id="9a009-145">Notice that the value for the `CircularString` example is close to 2&#x03c0; (2 \* pi), which is the actual circumference of the circle.</span></span>

### <a name="d-declaring-and-instantiating-a-geometry-instance-with-a-circularstring-in-the-same-statement"></a><span data-ttu-id="9a009-146">D:</span><span class="sxs-lookup"><span data-stu-id="9a009-146">D.</span></span> <span data-ttu-id="9a009-147">Deklarieren und Instanziieren einer Geometry-Instanz mit einem CircularString in derselben Anweisung</span><span class="sxs-lookup"><span data-stu-id="9a009-147">Declaring and Instantiating a Geometry Instance with a CircularString in the Same Statement</span></span>
 <span data-ttu-id="9a009-148">In diesem Codeausschnitt wird veranschaulicht, wie eine `geometry`-Instanz mit einem `CircularString` in derselben Anweisung deklariert und instanziiert wird:</span><span class="sxs-lookup"><span data-stu-id="9a009-148">This snippet shows how to declare and instantiate a `geometry` instance with a `CircularString` in the same statement:</span></span>

```sql
DECLARE @g geometry = 'CIRCULARSTRING(0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0)';
```

### <a name="e-instantiating-a-geography-instance-with-a-circularstring"></a><span data-ttu-id="9a009-149">E.</span><span class="sxs-lookup"><span data-stu-id="9a009-149">E.</span></span> <span data-ttu-id="9a009-150">Instanziieren einer Geography-Instanz mit einem CircularString</span><span class="sxs-lookup"><span data-stu-id="9a009-150">Instantiating a Geography Instance with a CircularString</span></span>
 <span data-ttu-id="9a009-151">Im folgenden Beispiel wird veranschaulicht, wie eine `geography`-Instanz mit einem `CircularString` deklariert und instanziiert wird:</span><span class="sxs-lookup"><span data-stu-id="9a009-151">The following example shows how to declare and instantiate a `geography` instance with a `CircularString`:</span></span>

```sql
DECLARE @g geography = 'CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653)';
```

### <a name="f-instantiating-a-geometry-instance-with-a-circularstring-that-is-a-straight-line"></a><span data-ttu-id="9a009-152">F.</span><span class="sxs-lookup"><span data-stu-id="9a009-152">F.</span></span> <span data-ttu-id="9a009-153">Instanziieren einer Geometry-Instanz mit einem CircularString, der eine Gerade darstellt</span><span class="sxs-lookup"><span data-stu-id="9a009-153">Instantiating a Geometry Instance with a CircularString that is a Straight Line</span></span>
 <span data-ttu-id="9a009-154">Im folgenden Beispiel wird veranschaulicht, wie eine `CircularString`-Instanz erstellt wird, die eine Gerade darstellt:</span><span class="sxs-lookup"><span data-stu-id="9a009-154">The following example shows how to create a `CircularString` instance that is a straight line:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::STGeomFromText('CIRCULARSTRING(0 0, 1 2, 2 4)', 0);
```

## <a name="see-also"></a><span data-ttu-id="9a009-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9a009-155">See Also</span></span>
 <span data-ttu-id="9a009-156">[Übersicht über räumliche Datentypen](spatial-data-types-overview.md) [: compoundcurve](compoundcurve.md) [MakeValid &#40;geography-Datentyp&#41;](/sql/t-sql/spatial-geography/makevalid-geography-data-type) [MakeValid &#40;Geometry](/sql/t-sql/spatial-geometry/makevalid-geometry-data-type) -Datentyp&#41;[STIsValid &#40;Geometry](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) -Datentyp&#41;[STIsValid &#40;geography](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) -Datentyp&#41;[STLength &#40;Geometry](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) -Datentyp&#41;[STStartPoint &#40;Geometry](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) -Datentyp&#41;[STEndpoint &#40;geometry-Datentyp&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [STPointN &#40;geometry-Datentyp&#41;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) [STNumPoints &#40;geometry-Datentyp&#41;](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) [STIsRing &#40;geometry-Datentyp&#41;](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) [STIsClosed &#40;Geometry](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) -Datentyp&#41;[STPointOnSurface &#40;geometry-Datentyp&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [LineString](linestring.md)</span><span class="sxs-lookup"><span data-stu-id="9a009-156">[Spatial Data Types Overview](spatial-data-types-overview.md) [CompoundCurve](compoundcurve.md) [MakeValid &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/makevalid-geography-data-type) [MakeValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/makevalid-geometry-data-type) [STIsValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) [STIsValid &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) [STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [STPointN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointn-geometry-data-type) [STNumPoints &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnumpoints-geometry-data-type) [STIsRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisring-geometry-data-type) [STIsClosed &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [LineString](linestring.md)</span></span>


