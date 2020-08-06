---
title: MultiPolygon | Microsoft-Dokumentation
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiPolygon geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 2c5db358-2a16-49d9-aac5-a74e86813932
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: f18fd2485c9b2e62586d9f3e81f76f6cf680dbfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621961"
---
# <a name="multipolygon"></a><span data-ttu-id="78052-102">MultiPolygon</span><span class="sxs-lookup"><span data-stu-id="78052-102">MultiPolygon</span></span>
  <span data-ttu-id="78052-103">Eine `MultiPolygon`-Instanz ist eine Sammlung von null oder mehr `Polygon`-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="78052-103">A `MultiPolygon` instance is a collection of zero or more `Polygon` instances.</span></span>

## <a name="polygon-instances"></a><span data-ttu-id="78052-104">Polygon-Instanzen</span><span class="sxs-lookup"><span data-stu-id="78052-104">Polygon Instances</span></span>
 <span data-ttu-id="78052-105">Die nachfolgende Abbildung enthält Beispiele für `MultiPolygon`-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="78052-105">The illustration below shows examples of `MultiPolygon` instances.</span></span>

 <span data-ttu-id="78052-106">![Beispiele für MultiPolygon-Geometrieinstanzen](../../database-engine/media/multipolygon.gif "Beispiele für MultiPolygon-Geometrieinstanzen")</span><span class="sxs-lookup"><span data-stu-id="78052-106">![Examples of geometry MultiPolygon instances](../../database-engine/media/multipolygon.gif "Examples of geometry MultiPolygon instances")</span></span>

 <span data-ttu-id="78052-107">Folgendes wird dargestellt:</span><span class="sxs-lookup"><span data-stu-id="78052-107">As shown in the illustration:</span></span>

-   <span data-ttu-id="78052-108">Abbildung 1 zeigt eine `MultiPolygon`-Instanz mit zwei `Polygon`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="78052-108">Figure 1 is a `MultiPolygon` instance with two `Polygon` elements.</span></span> <span data-ttu-id="78052-109">Die Begrenzung wird durch die beiden äußeren Ringe und die drei inneren Ringe definiert.</span><span class="sxs-lookup"><span data-stu-id="78052-109">The boundary is defined by the two exterior rings and the three interior rings.</span></span>

-   <span data-ttu-id="78052-110">Abbildung 2 zeigt eine `MultiPolygon`-Instanz mit zwei `Polygon`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="78052-110">Figure 2 is a `MultiPolygon` instance with two `Polygon` elements.</span></span> <span data-ttu-id="78052-111">Die Begrenzung wird durch die beiden äußeren Ringe und die drei inneren Ringe definiert.</span><span class="sxs-lookup"><span data-stu-id="78052-111">The boundary is defined by the two exterior rings and the three interior rings.</span></span> <span data-ttu-id="78052-112">Die beiden `Polygon`-Elemente überschneiden sich an einem Tangentenpunkt.</span><span class="sxs-lookup"><span data-stu-id="78052-112">The two `Polygon` elements intersect at a tangent point.</span></span>

### <a name="accepted-instances"></a><span data-ttu-id="78052-113">Akzeptierte Instanzen</span><span class="sxs-lookup"><span data-stu-id="78052-113">Accepted Instances</span></span>
 <span data-ttu-id="78052-114">Eine `MultiPolygon`-Instanz ist akzeptiert, wenn eine der folgenden Bedingungen erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="78052-114">A `MultiPolygon` instance is accepted one of the following conditions is met.</span></span>

-   <span data-ttu-id="78052-115">Es handelt sich um eine leere `MultiPolygon`-Instanz.</span><span class="sxs-lookup"><span data-stu-id="78052-115">It is an empty `MultiPolygon` instance.</span></span>

-   <span data-ttu-id="78052-116">Alle Instanzen, aus denen die `MultiPolygon`-Instanz besteht, sind akzeptierte `Polygon`-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="78052-116">All instances comprising the `MultiPolygon` instance are accepted `Polygon` instances.</span></span> <span data-ttu-id="78052-117">Weitere Informationen zu akzeptierten `Polygon` Instanzen finden Sie unter [Polygon](../spatial/polygon.md).</span><span class="sxs-lookup"><span data-stu-id="78052-117">For more information on accepted `Polygon` instances, see [Polygon](../spatial/polygon.md).</span></span>

 <span data-ttu-id="78052-118">In den folgenden Beispielen werden akzeptierte- `MultiPolygon` Instanzen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="78052-118">The following examples show accepted `MultiPolygon` instances.</span></span>

```
DECLARE @g1 geometry = 'MULTIPOLYGON EMPTY';
DECLARE @g2 geometry = 'MULTIPOLYGON(((1 1, 1 -1, -1 -1, -1 1, 1 1)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
DECLARE @g3 geometry = 'MULTIPOLYGON(((2 2, 2 -2, -2 -2, -2 2, 2 2)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
```

 <span data-ttu-id="78052-119">Das folgende Beispiel zeigt eine MultiPolygon-Instanz, die eine `System.FormatException`auslöst.</span><span class="sxs-lookup"><span data-stu-id="78052-119">The following example shows a MultiPolygon instance that will throw a `System.FormatException`.</span></span>

```
DECLARE @g geometry = 'MULTIPOLYGON(((1 1, 1 -1, -1 -1, -1 1, 1 1)),((1 1, 3 1, 3 3)))';
```

 <span data-ttu-id="78052-120">Die zweite Instanz im MultiPolygon ist eine LineString-Instanz und keine akzeptierte Polygon-Instanz.</span><span class="sxs-lookup"><span data-stu-id="78052-120">The second instance in the MultiPolygon is a LineString instance and not an accepted Polygon instance.</span></span>

### <a name="valid-instances"></a><span data-ttu-id="78052-121">Gültige Instanzen</span><span class="sxs-lookup"><span data-stu-id="78052-121">Valid Instances</span></span>
 <span data-ttu-id="78052-122">Eine `MultiPolygon`-Instanz ist gültig, wenn es sich um eine leere `MultiPolygon`-Instanz handelt bzw. wenn die folgenden Kriterien erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="78052-122">A `MultiPolygon` instance is valid if it is an empty `MultiPolygon` instance or if it meets the following criteria.</span></span>

1.  <span data-ttu-id="78052-123">Alle Instanzen, aus denen die `MultiPolygon`-Instanz besteht, sind gültige `Polygon`-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="78052-123">All of the instances comprising the `MultiPolygon` instance are valid `Polygon` instances.</span></span> <span data-ttu-id="78052-124">Informationen zu gültigen- `Polygon` Instanzen finden Sie unter [Polygon](../spatial/polygon.md).</span><span class="sxs-lookup"><span data-stu-id="78052-124">For valid `Polygon` instances, see [Polygon](../spatial/polygon.md).</span></span>

2.  <span data-ttu-id="78052-125">Die `Polygon`-Instanzen, aus denen die `MultiPolygon`-Instanz besteht, überschneiden sich nicht.</span><span class="sxs-lookup"><span data-stu-id="78052-125">None of the `Polygon` instances comprising the `MultiPolygon` instance overlap.</span></span>

 <span data-ttu-id="78052-126">Im folgende Beispiel werden zwei gültige `MultiPolygon`-Instanzen und eine ungültige `MultiPolygon`-Instanz veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="78052-126">The following example shows two valid `MultiPolygon` instances and one invalid `MultiPolygon` instance.</span></span>

```
DECLARE @g1 geometry = 'MULTIPOLYGON EMPTY';
DECLARE @g2 geometry = 'MULTIPOLYGON(((1 1, 1 -1, -1 -1, -1 1, 1 1)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
DECLARE @g3 geometry = 'MULTIPOLYGON(((2 2, 2 -2, -2 -2, -2 2, 2 2)),((1 1, 3 1, 3 3, 1 3, 1 1)))';
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid();
```

 <span data-ttu-id="78052-127">`@g2` ist gültig, da sich die zwei `Polygon`-Instanzen nur an einem Tangenspunkt berühren.</span><span class="sxs-lookup"><span data-stu-id="78052-127">`@g2` is valid because the two `Polygon` instances touch only at a tangent point.</span></span> <span data-ttu-id="78052-128">`@g3` ist ungültig, da sich die Innenbereiche der zwei `Polygon`-Instanzen überlappen.</span><span class="sxs-lookup"><span data-stu-id="78052-128">`@g3` is not valid because the interiors of the two `Polygon` instances overlap each other.</span></span>

## <a name="examples"></a><span data-ttu-id="78052-129">Beispiele</span><span class="sxs-lookup"><span data-stu-id="78052-129">Examples</span></span>
 <span data-ttu-id="78052-130">Im folgenden Beispiel wird die Erstellung einer `geometry``MultiPolygon` -Instanz veranschaulicht und das WKT-Format (Well-Known Text) der zweiten Komponente zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="78052-130">The following example shows the creation of a `geometry``MultiPolygon` instance and returns the Well-Known Text (WKT) of the second component.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::Parse('MULTIPOLYGON(((0 0, 0 3, 3 3, 3 0, 0 0), (1 1, 1 2, 2 1, 1 1)), ((9 9, 9 10, 10 9, 9 9)))');
SELECT @g.STGeometryN(2).STAsText();
```

 <span data-ttu-id="78052-131">In diesem Beispiel wird eine leere `MultiPolygon` -Instanz instantiiert.</span><span class="sxs-lookup"><span data-stu-id="78052-131">This example instantiates an empty `MultiPolygon` instance.</span></span>

```
DECLARE @g geometry;
SET @g = geometry::Parse('MULTIPOLYGON EMPTY');
```

## <a name="see-also"></a><span data-ttu-id="78052-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="78052-132">See Also</span></span>
 <span data-ttu-id="78052-133">[Polygon](../spatial/polygon.md) [-STArea &#40;geometry-Datentyp&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STCentroid &#40;Geometry](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) -Datentyp&#41;[STPointOnSurface &#40;Geometry](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) -Datentyp&#41;[räumliche Daten](../spatial/spatial-data-sql-server.md) &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="78052-133">[Polygon](../spatial/polygon.md) [STArea &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/starea-geometry-data-type) [STCentroid &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stcentroid-geometry-data-type) [STPointOnSurface &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stpointonsurface-geometry-data-type) [Spatial Data &#40;SQL Server&#41;](../spatial/spatial-data-sql-server.md)</span></span>


