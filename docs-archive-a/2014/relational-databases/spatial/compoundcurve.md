---
title: CompoundCurve | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: ae357f9b-e3e2-4cdf-af02-012acda2e466
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 6a899bbe9a17a64083592e1078e8cac93365f02b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609063"
---
# <a name="compoundcurve"></a><span data-ttu-id="62f8a-102">CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="62f8a-102">CompoundCurve</span></span>
  <span data-ttu-id="62f8a-103">Eine `CompoundCurve` ist eine Auflistung von 0 (null) oder mehr fortlaufenden `CircularString`-Instanzen oder `LineString`-Instanzen von geometry- oder geography-Typen.</span><span class="sxs-lookup"><span data-stu-id="62f8a-103">A `CompoundCurve` is a collection of zero or more continuous `CircularString` or `LineString` instances of either geometry or geography types.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="62f8a-104">Laden Sie für eine ausführliche Beschreibung und Beispiele der neuen räumlichen Funktionen in dieser Version, einschließlich des `CompoundCurve` unter Typs, das Whitepaper [neue räumliche Funktionen in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407)herunter.</span><span class="sxs-lookup"><span data-stu-id="62f8a-104">For a detailed description and examples of the new spatial features in this release, including the `CompoundCurve` subtype, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>

 <span data-ttu-id="62f8a-105">Eine leere `CompoundCurve`-Instanz kann instanziiert werden. Damit eine `CompoundCurve` gültig ist, muss sie jedoch die folgenden Kriterien erfüllen:</span><span class="sxs-lookup"><span data-stu-id="62f8a-105">An empty `CompoundCurve` instance can be instantiated, but for a `CompoundCurve` to be valid it must meet the following criteria:</span></span>

1.  <span data-ttu-id="62f8a-106">Sie muss mindestens eine `CircularString`-Instanz oder `LineString`-Instanz enthalten.</span><span class="sxs-lookup"><span data-stu-id="62f8a-106">It must contain at least one `CircularString` or `LineString` instance.</span></span>

2.  <span data-ttu-id="62f8a-107">Die Sequenz von `CircularString`-Instanzen oder `LineString`-Instanzen muss fortlaufend sein.</span><span class="sxs-lookup"><span data-stu-id="62f8a-107">The sequence of `CircularString` or `LineString` instances must be continuous.</span></span>

 <span data-ttu-id="62f8a-108">Wenn eine `CompoundCurve` eine Sequenz mehrerer `CircularString` -Instanzen und- `LineString` Instanzen enthält, muss der endendpunkt für jede Instanz mit Ausnahme der letzten Instanz der Start Endpunkt für die nächste Instanz in der Sequenz sein.</span><span class="sxs-lookup"><span data-stu-id="62f8a-108">If a `CompoundCurve` contains a sequence of multiple `CircularString` and `LineString` instances, the ending endpoint for every instance except for the last instance must be the starting endpoint for the next instance in the sequence.</span></span> <span data-ttu-id="62f8a-109">Wenn also der Endpunkt der vorhergehenden Instanz in der Sequenz (4 3 7 2) ist, muss der Anfangspunkt für die nächste Instanz in der Sequenz (4 3 7 2) sein.</span><span class="sxs-lookup"><span data-stu-id="62f8a-109">This means that if the ending point of a prior instance in the sequence is (4 3 7 2), the starting point for the next instance in the sequence must be (4 3 7 2).</span></span> <span data-ttu-id="62f8a-110">Beachten Sie, dass die Z-Werte (Höhe) und die M-Werte (Measure) für den Punkt ebenfalls gleich sein müssen.</span><span class="sxs-lookup"><span data-stu-id="62f8a-110">Note that Z(elevation) and M(measure) values for the point must also be the same.</span></span> <span data-ttu-id="62f8a-111">Wenn sich die beiden Punkte unterscheiden, wird ein `System.FormatException` ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="62f8a-111">If there is a difference in the two points, a `System.FormatException` is thrown.</span></span> <span data-ttu-id="62f8a-112">Punkte in einer `CircularString` müssen über keinen Z-Wert oder M-Wert verfügen.</span><span class="sxs-lookup"><span data-stu-id="62f8a-112">Points in a `CircularString` do not have to have a Z or M value.</span></span> <span data-ttu-id="62f8a-113">Wenn keine Z- oder M-Werte für den Endpunkt der vorherigen Instanz angegeben sind, kann der Anfangspunkt der nächsten Instanz keine Z- oder M-Werte einschließen.</span><span class="sxs-lookup"><span data-stu-id="62f8a-113">If no Z or M values are given for the ending point of the prior instance, the starting point of the next instance cannot include Z or M values.</span></span> <span data-ttu-id="62f8a-114">Wenn der Endpunkt für die vorherige Sequenz (4 3) ist, muss der Anfangspunkt für die nächste Sequenz (4 3) sein; (4 3 7 2) ist hingegen nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="62f8a-114">If the ending point for the prior sequence is (4 3), the starting point for the next sequence must be (4 3); it cannot be (4 3 7 2).</span></span> <span data-ttu-id="62f8a-115">Alle Punkte in einer `CompoundCurve`-Instanz dürfen entweder über keinen Z-Wert verfügen, oder sie müssen denselben Z-Wert aufweisen.</span><span class="sxs-lookup"><span data-stu-id="62f8a-115">All points in a `CompoundCurve` instance must have either no Z value or the same Z value.</span></span>

## <a name="compoundcurve-instances"></a><span data-ttu-id="62f8a-116">CompoundCurve-Instanzen</span><span class="sxs-lookup"><span data-stu-id="62f8a-116">CompoundCurve instances</span></span>
 <span data-ttu-id="62f8a-117">In der folgenden Abbildung sind gültige `CompoundCurve`-Typen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="62f8a-117">The following illustration shows valid `CompoundCurve` types.</span></span>

 ![](../../database-engine/media/f278742e-b861-4555-8b51-3d972b7602bf.png "f278742e-b861-4555-8b51-3d972b7602bf")

### <a name="accepted-instances"></a><span data-ttu-id="62f8a-118">Akzeptierte Instanzen</span><span class="sxs-lookup"><span data-stu-id="62f8a-118">Accepted instances</span></span>
 <span data-ttu-id="62f8a-119">Die `CompoundCurve`-Instanz wird akzeptiert, wenn sie leer ist bzw. die folgenden Kriterien erfüllt.</span><span class="sxs-lookup"><span data-stu-id="62f8a-119">`CompoundCurve` instance is accepted if it is an empty instance or meets the following criteria.</span></span>

1.  <span data-ttu-id="62f8a-120">Alle von der `CompoundCurve`-Instanz enthaltenen Instanzen sind akzeptierte Kreisbogensegment-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="62f8a-120">All the instances contained by `CompoundCurve` instance are accepted circular arc segment instances.</span></span> <span data-ttu-id="62f8a-121">Weitere Informationen zu akzeptierten Kreisbogensegment-Instanzen finden Sie unter [LineString](linestring.md) und [CircularString](circularstring.md).</span><span class="sxs-lookup"><span data-stu-id="62f8a-121">For more information on accepted circular arc segment instances, see [LineString](linestring.md) and [CircularString](circularstring.md).</span></span>

2.  <span data-ttu-id="62f8a-122">Alle Kreisbogensegmente in der `CompoundCurve`-Instanz sind verbunden.</span><span class="sxs-lookup"><span data-stu-id="62f8a-122">All of the circular arc segments in the `CompoundCurve` instance are connected.</span></span> <span data-ttu-id="62f8a-123">Der erste Punkt jedes nachfolgenden Kreisbogensegments entspricht dem letzten Punkt des jeweils vorgehenden Kreisbogensegments.</span><span class="sxs-lookup"><span data-stu-id="62f8a-123">The first point for each succeeding circular arc segment is the same as the last point on the preceding circular arc segment.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="62f8a-124">Dies schließt die Z- und M-Koordinaten ein.</span><span class="sxs-lookup"><span data-stu-id="62f8a-124">This includes the Z and M coordinates.</span></span> <span data-ttu-id="62f8a-125">Daher müssen alle vier Koordinaten X, Y, Z und M identisch sein.</span><span class="sxs-lookup"><span data-stu-id="62f8a-125">So, all four coordinates X, Y, Z, and M must be the same.</span></span>

3.  <span data-ttu-id="62f8a-126">Bei keiner der enthaltenen Instanzen handelt es sich um leere Instanzen.</span><span class="sxs-lookup"><span data-stu-id="62f8a-126">None of the contained instances are empty instances.</span></span>

 <span data-ttu-id="62f8a-127">Im folgenden Beispiel werden akzeptierte `CompoundCurve`-Instanzen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="62f8a-127">The following example shows accepted `CompoundCurve` instances.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE EMPTY';
DECLARE @g2 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 0, 0 1, -1 0), (-1 0, 2 0))';
```

 <span data-ttu-id="62f8a-128">Im folgenden Beispiel werden nicht akzeptierte `CompoundCurve`-Instanzen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="62f8a-128">The following example shows `CompoundCurve` instances that are not accepted.</span></span> <span data-ttu-id="62f8a-129">Diese Instanzen lösen eine `System.FormatException`aus.</span><span class="sxs-lookup"><span data-stu-id="62f8a-129">These instances throw `System.FormatException`.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE(CIRCULARSTRING EMPTY)';
DECLARE @g2 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 0, 0 1, -1 0), (1 0, 2 0))';
```

### <a name="valid-instances"></a><span data-ttu-id="62f8a-130">Gültige Instanzen</span><span class="sxs-lookup"><span data-stu-id="62f8a-130">Valid instances</span></span>
 <span data-ttu-id="62f8a-131">Eine `CompoundCurve`-Instanz ist gültig, wenn sie die folgenden Kriterien erfüllt.</span><span class="sxs-lookup"><span data-stu-id="62f8a-131">A `CompoundCurve` instance is valid if it meets the following criteria.</span></span>

1.  <span data-ttu-id="62f8a-132">Die `CompoundCurve`-Instanz wird akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="62f8a-132">The `CompoundCurve` instance is accepted.</span></span>

2.  <span data-ttu-id="62f8a-133">Alle in der `CompoundCurve`-Instanz enthaltenen Kreisbogensegment-Instanzen sind gültige Instanzen.</span><span class="sxs-lookup"><span data-stu-id="62f8a-133">All circular arc segment instances contained by the `CompoundCurve` instance are valid instances.</span></span>

 <span data-ttu-id="62f8a-134">Im folgenden Beispiel werden gültige `CompoundCurve`-Instanzen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="62f8a-134">The following example shows valid `CompoundCurve` instances.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE EMPTY';
DECLARE @g2 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 0, 0 1, -1 0), (-1 0, 2 0))';
DECLARE @g3 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 1, 1 1, 1 1), (1 1, 3 5, 5 4))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();

```

 <span data-ttu-id="62f8a-135">`@g3` ist gültig, da die `CircularString`-Instanz gültig ist.</span><span class="sxs-lookup"><span data-stu-id="62f8a-135">`@g3` is valid because the `CircularString` instance is valid.</span></span> <span data-ttu-id="62f8a-136">Weitere Informationen zur Gültigkeit der- `CircularString` Instanz finden Sie unter [circularstring](circularstring.md).</span><span class="sxs-lookup"><span data-stu-id="62f8a-136">For more information on the validity of the `CircularString` instance, see [CircularString](circularstring.md).</span></span>

 <span data-ttu-id="62f8a-137">Im folgenden Beispiel werden `CompoundCurve` -Instanzen veranschaulicht, die nicht gültig sind.</span><span class="sxs-lookup"><span data-stu-id="62f8a-137">The following example shows `CompoundCurve` instances that are not valid.</span></span>

```
DECLARE @g1 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 1, 1 1, 1 1), (1 1, 3 5, 5 4, 3 5))';
DECLARE @g2 geometry = 'COMPOUNDCURVE((1 1, 1 1))';
DECLARE @g3 geometry = 'COMPOUNDCURVE(CIRCULARSTRING(1 1, 2 3, 1 1))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();
```

 <span data-ttu-id="62f8a-138">`@g1` ist ungültig, da die zweite Instanz keine gültige LineString-Instanz ist.</span><span class="sxs-lookup"><span data-stu-id="62f8a-138">`@g1` is not valid because the second instance is not a valid LineString instance.</span></span> <span data-ttu-id="62f8a-139">`@g2` ist ungültig, da die `LineString`-Instanz ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="62f8a-139">`@g2` is not valid because the `LineString` instance is not valid.</span></span> <span data-ttu-id="62f8a-140">`@g3` ist ungültig, da die `CircularString`-Instanz ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="62f8a-140">`@g3` is not valid because the `CircularString` instance is not valid.</span></span> <span data-ttu-id="62f8a-141">Weitere Informationen zu gültigen `CircularString` -und- `LineString` Instanzen finden Sie unter [circularstring](circularstring.md) und [LineString](linestring.md).</span><span class="sxs-lookup"><span data-stu-id="62f8a-141">For more information on valid `CircularString` and `LineString` instances, see [CircularString](circularstring.md) and [LineString](linestring.md).</span></span>

## <a name="examples"></a><span data-ttu-id="62f8a-142">Beispiele</span><span class="sxs-lookup"><span data-stu-id="62f8a-142">Examples</span></span>

### <a name="a-instantiating-a-geometry-instance-with-an-empty-compooundcurve"></a><span data-ttu-id="62f8a-143">A.</span><span class="sxs-lookup"><span data-stu-id="62f8a-143">A.</span></span> <span data-ttu-id="62f8a-144">Instanziieren einer geometry-Instanz mit einer leeren CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="62f8a-144">Instantiating a geometry instance with an empty CompooundCurve</span></span>
 <span data-ttu-id="62f8a-145">Im folgenden Beispiel wird veranschaulicht, wie eine leere `CompoundCurve` -Instanz erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="62f8a-145">The following example shows how to create an empty `CompoundCurve` instance:</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE EMPTY');
```

### <a name="b-declaring-and-instantiating-a-geometry-instance-using-a-compoundcurve-in-the-same-statement"></a><span data-ttu-id="62f8a-146">B.</span><span class="sxs-lookup"><span data-stu-id="62f8a-146">B.</span></span> <span data-ttu-id="62f8a-147">Deklarieren und Instanziieren einer geometry-Instanz, die eine CompoundCurve in derselben Anweisung verwendet</span><span class="sxs-lookup"><span data-stu-id="62f8a-147">Declaring and instantiating a geometry instance using a CompoundCurve in the same statement</span></span>
 <span data-ttu-id="62f8a-148">Im folgenden Beispiel wird veranschaulicht, wie eine `geometry` -Instanz mit einer `CompoundCurve`in derselben Anweisung deklariert und instanziiert wird:</span><span class="sxs-lookup"><span data-stu-id="62f8a-148">The following example shows how to declare and initialize a `geometry` instance with a `CompoundCurve`in the same statement:</span></span>

```sql
DECLARE @g geometry = 'COMPOUNDCURVE ((2 2, 0 0),CIRCULARSTRING (0 0, 1 2.1082, 3 6.3246, 0 7, -3 6.3246, -1 2.1082, 0 0))';
```

### <a name="c-instantiating-a-geography-instance-with-a-compoundcurve"></a><span data-ttu-id="62f8a-149">C.</span><span class="sxs-lookup"><span data-stu-id="62f8a-149">C.</span></span> <span data-ttu-id="62f8a-150">Instanziieren einer geography-Instanz mit einer CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="62f8a-150">Instantiating a geography instance with a CompoundCurve</span></span>
 <span data-ttu-id="62f8a-151">Im folgenden Beispiel wird veranschaulicht, wie eine `geography`-Instanz mit einer `CompoundCurve` deklariert und initialisiert wird:</span><span class="sxs-lookup"><span data-stu-id="62f8a-151">The following example shows how to declare and initialize a `geography` instance with a `CompoundCurve`:</span></span>

```sql
DECLARE @g geography = 'COMPOUNDCURVE(CIRCULARSTRING(-122.358 47.653, -122.348 47.649, -122.348 47.658, -122.358 47.658, -122.358 47.653))';
```

### <a name="d-storing-a-square-in-a-compoundcurve-instance"></a><span data-ttu-id="62f8a-152">D:</span><span class="sxs-lookup"><span data-stu-id="62f8a-152">D.</span></span> <span data-ttu-id="62f8a-153">Speichern eines Quadrats in einer CompoundCurve-Instanz</span><span class="sxs-lookup"><span data-stu-id="62f8a-153">Storing a square in a CompoundCurve instance</span></span>
 <span data-ttu-id="62f8a-154">Im folgenden Beispiel werden zwei verschiedene Möglichkeiten gezeigt, wie mithilfe einer `CompoundCurve` -Instanz ein Quadrat gespeichert werden kann.</span><span class="sxs-lookup"><span data-stu-id="62f8a-154">The following example uses two different ways to use a `CompoundCurve` instance to store a square.</span></span>

```sql
DECLARE @g1 geometry, @g2 geometry;
SET @g1 = geometry::Parse('COMPOUNDCURVE((1 1, 1 3), (1 3, 3 3),(3 3, 3 1), (3 1, 1 1))');
SET @g2 = geometry::Parse('COMPOUNDCURVE((1 1, 1 3, 3 3, 3 1, 1 1))');
SELECT @g1.STLength(), @g2.STLength();
```

 <span data-ttu-id="62f8a-155">Die Länge von `@g1` und die Länge von `@g2` sind identisch.</span><span class="sxs-lookup"><span data-stu-id="62f8a-155">The lengths for both `@g1` and `@g2` are the same.</span></span> <span data-ttu-id="62f8a-156">Anhand des Beispiels können Sie feststellen, dass von einer `CompoundCurve`-Instanz eine oder mehrere Instanzen von `LineString` gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="62f8a-156">Notice from the example that a `CompoundCurve` instance can store one or more instances of `LineString`.</span></span>

### <a name="e-instantiating-a-geometry-instance-using-a-compoundcurve-with-multiple-circularstrings"></a><span data-ttu-id="62f8a-157">E.</span><span class="sxs-lookup"><span data-stu-id="62f8a-157">E.</span></span> <span data-ttu-id="62f8a-158">Instanziieren einer geometry-Instanz mithilfe einer CompoundCurve mit mehreren CircularStrings</span><span class="sxs-lookup"><span data-stu-id="62f8a-158">Instantiating a geometry instance using a CompoundCurve with multiple CircularStrings</span></span>
 <span data-ttu-id="62f8a-159">Im folgenden Beispiel wird gezeigt, wie mithilfe von zwei verschiedenen `CircularString` -Instanzen eine `CompoundCurve`initialisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="62f8a-159">The following example shows how to use two different `CircularString` instances to initialize a `CompoundCurve`.</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), CIRCULARSTRING(4 2, 2 4, 0 2))');
SELECT @g.STLength();
```

 <span data-ttu-id="62f8a-160">Dadurch wird die folgende Ausgabe erzeugt: 12,566370... Dies entspricht 4&#x03c0; (4 \* PI).</span><span class="sxs-lookup"><span data-stu-id="62f8a-160">This produces the following output: 12.566370... which is the equivalent of 4&#x03c0; (4 \* pi).</span></span> <span data-ttu-id="62f8a-161">Von der `CompoundCurve` -Instanz im Beispiel wird ein Kreis mit dem Radius 2 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="62f8a-161">The `CompoundCurve` instance in the example stores a circle with a radius of 2.</span></span> <span data-ttu-id="62f8a-162">In den beiden vorherigen Codebeispielen musste keine `CompoundCurve`verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="62f8a-162">Both of the previous code examples did not have to use a `CompoundCurve`.</span></span> <span data-ttu-id="62f8a-163">Für das erste Beispiel wäre eine `LineString` -Instanz einfacher gewesen, während sich für das zweite Beispiel eher eine `CircularString` -Instanz empfiehlt.</span><span class="sxs-lookup"><span data-stu-id="62f8a-163">For the first example a `LineString` instance would have been simpler, and a `CircularString` instance would have been simpler for the second example.</span></span> <span data-ttu-id="62f8a-164">Im nächsten Beispiel wird jedoch verdeutlich, in welchen Fällen eine `CompoundCurve` eine bessere Alternative darstellt.</span><span class="sxs-lookup"><span data-stu-id="62f8a-164">However, the next example shows where a `CompoundCurve` provides a better alternative.</span></span>

### <a name="f-using-a-compoundcurve-to-store-a-semicircle"></a><span data-ttu-id="62f8a-165">F.</span><span class="sxs-lookup"><span data-stu-id="62f8a-165">F.</span></span> <span data-ttu-id="62f8a-166">Speichern eines Halbkreises mithilfe einer CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="62f8a-166">Using a CompoundCurve to store a semicircle</span></span>
 <span data-ttu-id="62f8a-167">Im folgenden Beispiel wird ein Halbkreis mithilfe einer `CompoundCurve` -Instanz gespeichert.</span><span class="sxs-lookup"><span data-stu-id="62f8a-167">The following example uses a `CompoundCurve` instance to store a semicircle.</span></span>

```sql
DECLARE @g geometry;
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), (4 2, 0 2))');
SELECT @g.STLength();
```

### <a name="g-storing-multiple-circularstring-and-linestring-instances-in-a-compoundcurve"></a><span data-ttu-id="62f8a-168">G.</span><span class="sxs-lookup"><span data-stu-id="62f8a-168">G.</span></span> <span data-ttu-id="62f8a-169">Speichern mehrerer CircularString- und LineString-Instanzen in einer CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="62f8a-169">Storing multiple CircularString and LineString instances in a CompoundCurve</span></span>
 <span data-ttu-id="62f8a-170">Im folgenden Beispiel wird gezeigt, wie mehrere `CircularString` -Instanzen und `LineString` -Instanzen mit einer `CompoundCurve`gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="62f8a-170">The following example shows how multiple `CircularString` and `LineString` instances can be stored by using a `CompoundCurve`.</span></span>

```sql
DECLARE @g geometry
SET @g = geometry::Parse('COMPOUNDCURVE((3 5, 3 3), CIRCULARSTRING(3 3, 5 1, 7 3), (7 3, 7 5), CIRCULARSTRING(7 5, 5 7, 3 5))');
SELECT @g.STLength();
```

### <a name="h-storing-instances-with-z-and-m-values"></a><span data-ttu-id="62f8a-171">H.</span><span class="sxs-lookup"><span data-stu-id="62f8a-171">H.</span></span> <span data-ttu-id="62f8a-172">Speichern von Instanzen mit Z- und M-Werten</span><span class="sxs-lookup"><span data-stu-id="62f8a-172">Storing instances with Z and M values</span></span>
 <span data-ttu-id="62f8a-173">Im folgenden Beispiel wird veranschaulicht, wie mithilfe einer `CompoundCurve` -Instanz eine Sequenz von `CircularString` -Instanzen und `LineString` -Instanzen mit Z- und M-Werten gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="62f8a-173">The following example shows how to use a `CompoundCurve` instance to store a sequence of `CircularString` and `LineString` instances with both Z and M values.</span></span>

```sql
SET @g = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(7 5 4 2, 5 7 4 2, 3 5 4 2), (3 5 4 2, 8 7 4 2))');
```

### <a name="i-illustrating-why-circularstring-instances-must-be-explicitly-declared"></a><span data-ttu-id="62f8a-174">I.</span><span class="sxs-lookup"><span data-stu-id="62f8a-174">I.</span></span> <span data-ttu-id="62f8a-175">Gründe für die explizite Deklaration von CircularString-Instanzen</span><span class="sxs-lookup"><span data-stu-id="62f8a-175">Illustrating why CircularString instances must be explicitly declared</span></span>
 <span data-ttu-id="62f8a-176">Im folgenden Beispiel wird erläutert, weshalb `CircularString` -Instanzen explizit deklariert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="62f8a-176">The following example shows why `CircularString` instances must be explicitly declared.</span></span> <span data-ttu-id="62f8a-177">Der Programmierer versucht, in einer `CompoundCurve` -Instanz einen Kreis zu speichern.</span><span class="sxs-lookup"><span data-stu-id="62f8a-177">The programmer is trying to store a circle in a `CompoundCurve` instance.</span></span>

```sql
DECLARE @g1 geometry;  
DECLARE @g2 geometry;
SET @g1 = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), (4 2, 2 4, 0 2))');
SELECT 'Circle One', @g1.STLength() AS Perimeter;  -- gives an inaccurate amount
SET @g2 = geometry::Parse('COMPOUNDCURVE(CIRCULARSTRING(0 2, 2 0, 4 2), CIRCULARSTRING(4 2, 2 4, 0 2))');
SELECT 'Circle Two', @g2.STLength() AS Perimeter;  -- now we get an accurate amount
```

 <span data-ttu-id="62f8a-178">Die Ausgabe lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="62f8a-178">The output is as follows:</span></span>

```
Circle One11.940039...
Circle Two12.566370...
```

 <span data-ttu-id="62f8a-179">Der Umkreis für Circle Two ist ungefähr 4&#x03c0; (4 \* PI), der tatsächliche Wert für den Umkreis.</span><span class="sxs-lookup"><span data-stu-id="62f8a-179">The perimeter for Circle Two is approximately 4&#x03c0; (4 \* pi), which is the actual value for the perimeter.</span></span> <span data-ttu-id="62f8a-180">Der Umkreis für Circle One ist jedoch sehr ungenau.</span><span class="sxs-lookup"><span data-stu-id="62f8a-180">However, the perimeter for Circle One is significantly inaccurate.</span></span> <span data-ttu-id="62f8a-181">Durch die `CompoundCurve` -Instanz von Circle One werden ein Kreisbogensegment (ABC) und zwei Liniensegmente (CD, DA) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="62f8a-181">Circle One's `CompoundCurve` instance stores one circular arc segment (ABC) and two line segments (CD, DA).</span></span> <span data-ttu-id="62f8a-182">Von der `CompoundCurve` -Instanz müssen zwei Kreisbogensegmente (ABC, CDA) gespeichert werden, um einen Kreis zu definieren.</span><span class="sxs-lookup"><span data-stu-id="62f8a-182">The `CompoundCurve` instance has to store two circular arc segments (ABC, CDA) to define a circle.</span></span> <span data-ttu-id="62f8a-183">Eine `LineString` -Instanz definiert die zweite Punktmenge (4 2, 2 4, 0 2) in der `CompoundCurve` -Instanz von Circle One.</span><span class="sxs-lookup"><span data-stu-id="62f8a-183">A `LineString` instance defines the second set of points (4 2, 2 4, 0 2) in Circle One's `CompoundCurve` instance.</span></span> <span data-ttu-id="62f8a-184">Sie müssen in einer `CircularString` explizit eine `CompoundCurve`-Instanz deklarieren.</span><span class="sxs-lookup"><span data-stu-id="62f8a-184">You have to explicitly declare a `CircularString` instance inside a `CompoundCurve`.</span></span>

## <a name="see-also"></a><span data-ttu-id="62f8a-185">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="62f8a-185">See Also</span></span>
 <span data-ttu-id="62f8a-186">[STIsValid &#40;geometry-Datentyp&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) [STLength &#40;geometry-Datentyp&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry-Datentyp&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;geometry-Datentyp&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [LineString](linestring.md) [circularstring](circularstring.md) [räumliche Datentypen Übersichts](spatial-data-types-overview.md) [Punkt](point.md)</span><span class="sxs-lookup"><span data-stu-id="62f8a-186">[STIsValid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisvalid-geometry-data-type) [STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) [STStartPoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/ststartpoint-geometry-data-type) [STEndpoint &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stendpoint-geometry-data-type) [LineString](linestring.md) [CircularString](circularstring.md) [Spatial Data Types Overview](spatial-data-types-overview.md) [Point](point.md)</span></span>


