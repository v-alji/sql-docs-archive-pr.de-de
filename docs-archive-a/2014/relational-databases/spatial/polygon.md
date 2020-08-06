---
title: Polygon | Microsoft-Dokumentation
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geometry subtypes [SQL Server]
- Polygon geometry subtype [SQL Server]
ms.assetid: b6a21c3c-fdb8-4187-8229-1c488454fdfb
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 040bb8a2558cc57b1b99a3ce984bec3c8925bc0d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621957"
---
# <a name="polygon"></a><span data-ttu-id="9304f-102">Polygon</span><span class="sxs-lookup"><span data-stu-id="9304f-102">Polygon</span></span>
  <span data-ttu-id="9304f-103">Ein `Polygon` ist eine zweidimensionale Fläche, die als Sequenz von Punkten gespeichert wird, die einen äußeren Begrenzungsring und null oder mehrere innere Ringe definieren.</span><span class="sxs-lookup"><span data-stu-id="9304f-103">A `Polygon` is a two-dimensional surface stored as a sequence of points defining an exterior bounding ring and zero or more interior rings.</span></span>

## <a name="polygon-instances"></a><span data-ttu-id="9304f-104">Polygon-Instanzen</span><span class="sxs-lookup"><span data-stu-id="9304f-104">Polygon instances</span></span>
 <span data-ttu-id="9304f-105">Eine `Polygon`-Instanz kann aus einem Ring gebildet werden, der wenigstens drei unterschiedliche Punkte besitzt.</span><span class="sxs-lookup"><span data-stu-id="9304f-105">A `Polygon` instance can be formed from a ring that has at least three distinct points.</span></span> <span data-ttu-id="9304f-106">Eine `Polygon`-Instanz kann auch leer sein.</span><span class="sxs-lookup"><span data-stu-id="9304f-106">A `Polygon` instance can also be empty.</span></span>

 <span data-ttu-id="9304f-107">Der äußere und eventuelle innere Ring einer `Polygon`-Instanz definieren die Begrenzung.</span><span class="sxs-lookup"><span data-stu-id="9304f-107">The exterior and any interior rings of a `Polygon` define its boundary.</span></span> <span data-ttu-id="9304f-108">Der Raum innerhalb der Ringe definiert das Innere des `Polygon`s.</span><span class="sxs-lookup"><span data-stu-id="9304f-108">The space within the rings defines the interior of the `Polygon`.</span></span>

 <span data-ttu-id="9304f-109">Die nachfolgende Abbildung enthält Beispiele für `Polygon`-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="9304f-109">The illustration below shows examples of `Polygon` instances.</span></span>

 <span data-ttu-id="9304f-110">![Beispiele von Polygon-Geometrieinstanzen](../../database-engine/media/polygon.gif "Beispiele von Polygon-Geometrieinstanzen")</span><span class="sxs-lookup"><span data-stu-id="9304f-110">![Examples of geometry Polygon instances](../../database-engine/media/polygon.gif "Examples of geometry Polygon instances")</span></span>

 <span data-ttu-id="9304f-111">Folgendes wird dargestellt:</span><span class="sxs-lookup"><span data-stu-id="9304f-111">As shown in the illustration:</span></span>

1.  <span data-ttu-id="9304f-112">Abbildung 1 zeigt eine `Polygon`-Instanz, deren Begrenzung von einem äußeren Ring definiert wird.</span><span class="sxs-lookup"><span data-stu-id="9304f-112">Figure 1 is a `Polygon` instance whose boundary is defined by an exterior ring.</span></span>

2.  <span data-ttu-id="9304f-113">Abbildung 2 zeigt eine `Polygon`-Instanz, deren Begrenzung von einem äußeren Ring und zwei inneren Ringen definiert wird.</span><span class="sxs-lookup"><span data-stu-id="9304f-113">Figure 2 is a `Polygon` instance whose boundary is defined by an exterior ring and two interior rings.</span></span> <span data-ttu-id="9304f-114">Der Bereich zwischen den inneren Ringen ist Teil des äußeren Rings der `Polygon`-Instanz.</span><span class="sxs-lookup"><span data-stu-id="9304f-114">The area inside the interior rings is part of the exterior of the `Polygon` instance.</span></span>

3.  <span data-ttu-id="9304f-115">Abbildung 3 ist eine gültige `Polygon`-Instanz, da sich seine inneren Ringe an einem einzelnen Tangentialpunkt schneiden.</span><span class="sxs-lookup"><span data-stu-id="9304f-115">Figure 3 is a valid `Polygon` instance because its interior rings intersect at a single tangent point.</span></span>

### <a name="accepted-instances"></a><span data-ttu-id="9304f-116">Akzeptierte Instanzen</span><span class="sxs-lookup"><span data-stu-id="9304f-116">Accepted instances</span></span>
 <span data-ttu-id="9304f-117">Akzeptierte `Polygon`-Instanzen sind Instanzen, die in einer `geometry`-Variablen oder einer `geography`-Variablen gespeichert werden können, ohne dass eine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="9304f-117">Accepted `Polygon` instances are instances that can be stored in a `geometry` or `geography` variable without throwing an exception.</span></span> <span data-ttu-id="9304f-118">Bei den folgenden `Polygon`-Instanzen handelt es sich um akzeptierte Instanzen:</span><span class="sxs-lookup"><span data-stu-id="9304f-118">The following are accepted `Polygon` instances:</span></span>

-   <span data-ttu-id="9304f-119">Eine leere `Polygon`-Instanz</span><span class="sxs-lookup"><span data-stu-id="9304f-119">An Empty `Polygon` instance</span></span>

-   <span data-ttu-id="9304f-120">Eine `Polygon`-Instanz, die einen akzeptablen äußeren Ring und null oder mehr akzeptable innere Ringe aufweist</span><span class="sxs-lookup"><span data-stu-id="9304f-120">A `Polygon` instance that has an acceptable exterior ring and zero or more acceptable interior rings</span></span>

 <span data-ttu-id="9304f-121">Die folgenden Kriterien müssen erfüllt sein, damit ein Ring akzeptabel ist.</span><span class="sxs-lookup"><span data-stu-id="9304f-121">The following criteria are needed for a ring to be acceptable.</span></span>

-   <span data-ttu-id="9304f-122">Die `LineString`-Instanz muss akzeptiert sein.</span><span class="sxs-lookup"><span data-stu-id="9304f-122">The `LineString` instance must be accepted.</span></span>

-   <span data-ttu-id="9304f-123">Die `LineString`-Instanz muss über mindestens vier Punkte verfügen.</span><span class="sxs-lookup"><span data-stu-id="9304f-123">The `LineString` instance must have at least four points.</span></span>

-   <span data-ttu-id="9304f-124">Der Anfangspunkt und der Endpunkt der `LineString`-Instanz müssen identisch sein.</span><span class="sxs-lookup"><span data-stu-id="9304f-124">The starting and ending points of the `LineString` instance must be the same.</span></span>

 <span data-ttu-id="9304f-125">Im folgenden Beispiel werden akzeptierte `Polygon`-Instanzen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9304f-125">The following example shows accepted `Polygon` instances.</span></span>

```
DECLARE @g1 geometry = 'POLYGON EMPTY';
DECLARE @g2 geometry = 'POLYGON((1 1, 3 3, 3 1, 1 1))';
DECLARE @g3 geometry = 'POLYGON((-5 -5, -5 5, 5 5, 5 -5, -5 -5),(0 0, 3 0, 3 3, 0 3, 0 0))';
DECLARE @g4 geometry = 'POLYGON((-5 -5, -5 5, 5 5, 5 -5, -5 -5),(3 0, 6 0, 6 3, 3 3, 3 0))';
DECLARE @g5 geometry = 'POLYGON((1 1, 1 1, 1 1, 1 1))';
```

 <span data-ttu-id="9304f-126">Wie `@g4` und `@g5` zeigen, ist es möglich, dass eine akzeptierte `Polygon`-Instanz keine gültige `Polygon`-Instanz ist.</span><span class="sxs-lookup"><span data-stu-id="9304f-126">As `@g4` and `@g5` show an accepted `Polygon` instance may not be a valid `Polygon` instance.</span></span> <span data-ttu-id="9304f-127">`@g5` zeigt auch, dass eine Polygon-Instanz nur einen Ring mit vier beliebigen Punkten enthalten muss, um akzeptiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="9304f-127">`@g5` also shows that a Polygon instance needs to only contain a ring with any four points to be accepted.</span></span>

 <span data-ttu-id="9304f-128">In den folgenden Beispielen wird eine `System.FormatException` ausgelöst, da die `Polygon`-Instanzen nicht akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="9304f-128">The following examples throw a `System.FormatException` because the `Polygon` instances are not accepted.</span></span>

```
DECLARE @g1 geometry = 'POLYGON((1 1, 3 3, 1 1))';
DECLARE @g2 geometry = 'POLYGON((1 1, 3 3, 3 1, 1 5))';
```

 <span data-ttu-id="9304f-129">`@g1` wird nicht akzeptiert, da die `LineString`-Instanz für den äußeren Ring nicht genug Punkte enthält.</span><span class="sxs-lookup"><span data-stu-id="9304f-129">`@g1` is not accepted because the `LineString` instance for the exterior ring does not contain enough points.</span></span> <span data-ttu-id="9304f-130">`@g2` wird nicht akzeptiert, da die `LineString`-Instanz des Ausgangspunkts des äußeren Rings nicht dem Endpunkt entspricht.</span><span class="sxs-lookup"><span data-stu-id="9304f-130">`@g2` is not accepted because the starting point of the exterior ring `LineString` instance is not the same as the ending point.</span></span> <span data-ttu-id="9304f-131">Im folgenden Beispiel ist ein akzeptabler äußerer Ring enthalten, der innere Ring hingegen ist nicht akzeptabel.</span><span class="sxs-lookup"><span data-stu-id="9304f-131">The following example has an acceptable exterior ring, but the interior ring is not acceptable.</span></span> <span data-ttu-id="9304f-132">Dadurch wird auch eine `System.FormatException`ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9304f-132">This also throws a `System.FormatException`.</span></span>

```
DECLARE @g geometry = 'POLYGON((-5 -5, -5 5, 5 5, 5 -5, -5 -5),(0 0, 3 0, 0 0))';
```

### <a name="valid-instances"></a><span data-ttu-id="9304f-133">Gültige Instanzen</span><span class="sxs-lookup"><span data-stu-id="9304f-133">Valid instances</span></span>
 <span data-ttu-id="9304f-134">Die inneren Ringe eines `Polygon`s können sich selbst und einander an einzelnen Tangentialpunkten berühren; überkreuzen sich die inneren Ringe eines `Polygon`s jedoch, ist die Instanz ungültig.</span><span class="sxs-lookup"><span data-stu-id="9304f-134">The interior rings of a `Polygon` can touch both themselves and each other at single tangent points, but if the interior rings of a `Polygon` cross, the instance is not valid.</span></span>

 <span data-ttu-id="9304f-135">Im folgenden Beispiel werden gültige `Polygon`-Instanzen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9304f-135">The following example shows valid `Polygon` instances.</span></span>

```
DECLARE @g1 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20))';
DECLARE @g2 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0))';
DECLARE @g3 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (-10 0, 0 10, -5 -10, -10 0))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();
```

 <span data-ttu-id="9304f-136">`@g3` ist gültig, da die zwei inneren Ringe einen einzigen Punkt berühren und einander nicht schneiden.</span><span class="sxs-lookup"><span data-stu-id="9304f-136">`@g3` is valid because the two interior rings touch at a single point and do not cross each other.</span></span> <span data-ttu-id="9304f-137">Im folgenden Beispiel werden `Polygon` -Instanzen veranschaulicht, die nicht gültig sind.</span><span class="sxs-lookup"><span data-stu-id="9304f-137">The following example shows `Polygon` instances that are not valid.</span></span>

```
DECLARE @g1 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (20 0, 0 10, 0 -20, 20 0))';
DECLARE @g2 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (5 0, 1 5, 1 -5, 5 0))';
DECLARE @g3 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (-10 0, 0 10, 0 -10, -10 0))';
DECLARE @g4 geometry = 'POLYGON((-20 -20, -20 20, 20 20, 20 -20, -20 -20), (10 0, 0 10, 0 -10, 10 0), (-10 0, 1 5, 0 -10, -10 0))';
DECLARE @g5 geometry = 'POLYGON((10 0, 0 10, 0 -10, 10 0), (-20 -20, -20 20, 20 20, 20 -20, -20 -20) )';
DECLARE @g6 geometry = 'POLYGON((1 1, 1 1, 1 1, 1 1))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid(), @g5.STIsValid(), @g6.STIsValid();
```

 <span data-ttu-id="9304f-138">`@g1` ist ungültig, da der innere Ring den äußeren Ring an zwei Stellen berührt.</span><span class="sxs-lookup"><span data-stu-id="9304f-138">`@g1` is not valid because the inner ring touches the exterior ring in two places.</span></span> <span data-ttu-id="9304f-139">`@g2` ist ungültig, da der zweite innere Ring im Inneren des ersten inneren Rings liegt.</span><span class="sxs-lookup"><span data-stu-id="9304f-139">`@g2` is not valid because the second inner ring in within the interior of the first inner ring.</span></span> <span data-ttu-id="9304f-140">`@g3` ist ungültig, da sich die zwei inneren Ringe an mehreren aufeinander folgenden Punkten berühren.</span><span class="sxs-lookup"><span data-stu-id="9304f-140">`@g3` is not valid because the two inner rings touch at multiple consecutive points.</span></span> <span data-ttu-id="9304f-141">`@g4` ist ungültig, da sich das Innere der zwei inneren Ringe überlappt.</span><span class="sxs-lookup"><span data-stu-id="9304f-141">`@g4` is not valid because the interiors of the two inner rings overlap.</span></span> <span data-ttu-id="9304f-142">`@g5` ist ungültig, da der äußere Ring nicht der erste Ring ist.</span><span class="sxs-lookup"><span data-stu-id="9304f-142">`@g5` is not valid because the exterior ring is not the first ring.</span></span> <span data-ttu-id="9304f-143">`@g6` ist ungültig, da der Ring nicht mindestens drei unterschiedliche Punkte aufweist.</span><span class="sxs-lookup"><span data-stu-id="9304f-143">`@g6` is not valid because the ring does not have at least three distinct points.</span></span>

## <a name="examples"></a><span data-ttu-id="9304f-144">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9304f-144">Examples</span></span>
 <span data-ttu-id="9304f-145">Im folgenden Beispiel wird eine einfache `geometry``Polygon` mit einem Loch und dem SRID 10 erstellt.</span><span class="sxs-lookup"><span data-stu-id="9304f-145">The following example creates a simple `geometry``Polygon` instance with a hole and SRID 10.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::STPolyFromText('POLYGON((0 0, 0 3, 3 3, 3 0, 0 0), (1 1, 1 2, 2 1, 1 1))', 10);
```

 <span data-ttu-id="9304f-146">Eine Instanz, die nicht gültig ist, kann eingegeben und in eine gültige `geometry` -Instanz konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="9304f-146">Aninstance that is not valid may be entered and converted to a valid `geometry` instance.</span></span> <span data-ttu-id="9304f-147">Im folgenden Beispiel für ein `Polygon`überlappen die inneren Ringe und der äußere Ring, weshalb die Instanz ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="9304f-147">In the following example of a `Polygon`, the interior and exterior rings overlap and the instance is not valid.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::Parse('POLYGON((1 0, 0 1, 1 2, 2 1, 1 0), (2 0, 1 1, 2 2, 3 1, 2 0))');
```

 <span data-ttu-id="9304f-148">Im folgenden Beispiel wird die ungültige Instanz mit `MakeValid()`in eine gültige konvertiert.</span><span class="sxs-lookup"><span data-stu-id="9304f-148">In the following example, the invalid instance is made valid with `MakeValid()`.</span></span>

```
SET @g = @g.MakeValid();
SELECT @g.ToString();
```

 <span data-ttu-id="9304f-149">Die vom oben erwähnten Beispiel zurückgegebene `geometry` -Instanz ist ein `MultiPolygon`.</span><span class="sxs-lookup"><span data-stu-id="9304f-149">The `geometry` instance returned from the above example is a `MultiPolygon`.</span></span>

```
MULTIPOLYGON (((2 0, 3 1, 2 2, 1.5 1.5, 2 1, 1.5 0.5, 2 0)), ((1 0, 1.5 0.5, 1 1, 1.5 1.5, 1 2, 0 1, 1 0)))
```

 <span data-ttu-id="9304f-150">Es folgt ein weiteres Beispiel zum Konvertieren einer ungültigen Instanz in eine gültige geometry-Instanz.</span><span class="sxs-lookup"><span data-stu-id="9304f-150">Here is another example of converting an invalid instance to a valid geometry instance.</span></span> <span data-ttu-id="9304f-151">Im folgenden Beispiel wurde die `Polygon` -Instanz mit drei Punkten erstellt, die identisch sind:</span><span class="sxs-lookup"><span data-stu-id="9304f-151">In the following example the `Polygon` instance has been created using three points that are exactly the same:</span></span>

```sql
DECLARE @g geometry
SET @g = geometry::Parse('POLYGON((1 3, 1 3, 1 3, 1 3))');
SET @g = @g.MakeValid();
SELECT @g.ToString()
```

 <span data-ttu-id="9304f-152">Die oben zurückgegebene geometry-Instanz ist ein `Point(1 3)`.</span><span class="sxs-lookup"><span data-stu-id="9304f-152">The geometry instance returned above is a `Point(1 3)`.</span></span>  <span data-ttu-id="9304f-153">Wenn das angegebene `Polygon` gleich `POLYGON((1 3, 1 5, 1 3, 1 3))` ist, gibt `MakeValid()``LINESTRING(1 3, 1 5)`zurück.</span><span class="sxs-lookup"><span data-stu-id="9304f-153">If the `Polygon` given is `POLYGON((1 3, 1 5, 1 3, 1 3))` then `MakeValid()` would return `LINESTRING(1 3, 1 5)`.</span></span>

## <a name="see-also"></a><span data-ttu-id="9304f-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9304f-154">See Also</span></span>
 <span data-ttu-id="9304f-155">[STArea &#40;geometry-Datentyp&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STExteriorRing &#40;geometry-Datentyp&#41;](/sql/t-sql/spatial-geometry/stexteriorring-geometry-data-type) [STNumInteriorRing &#40;geometry-Datentyp](/sql/t-sql/spatial-geometry/stnuminteriorring-geometry-data-type) [&#41;STInteriorRingN &#40;geometry-Datentyp](/sql/t-sql/spatial-geometry/stinteriorringn-geometry-data-type)&#41;[STCentroid](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) &#40;geometry-Datentyp&#41;[STPointOnSurface &#40;geometry-Datentyps](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [&#41;&#40;](../spatial/polygon.md) für den geometry-Datentyp SQL Server&#41;&#40;den geometry-Datentyp&#41;[Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) [STIsValid &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) [STIsValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type)</span><span class="sxs-lookup"><span data-stu-id="9304f-155">[STArea &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STExteriorRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stexteriorring-geometry-data-type) [STNumInteriorRing &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stnuminteriorring-geometry-data-type) [STInteriorRingN &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stinteriorringn-geometry-data-type) [STCentroid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [MultiPolygon](../spatial/polygon.md) [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md) [STIsValid &#40;geography Data Type&#41;](/sql/t-sql/spatial-geography/stisvalid-geography-data-type) [STIsValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type)</span></span>


