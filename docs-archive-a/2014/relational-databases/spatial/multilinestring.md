---
title: MultiLineString | Microsoft-Dokumentation
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiLineString geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 95deeefe-d6c5-4a11-b347-379e4486e7b7
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: fdd093d99d055df8e15fc22e3e570e6805e35d6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621965"
---
# <a name="multilinestring"></a><span data-ttu-id="e458c-102">MultiLineString</span><span class="sxs-lookup"><span data-stu-id="e458c-102">MultiLineString</span></span>
  <span data-ttu-id="e458c-103">Eine `MultiLineString` ist eine Auflistung von NULL oder mehr- `geometry` oder **geographylinestring** -Instanzen.</span><span class="sxs-lookup"><span data-stu-id="e458c-103">A `MultiLineString` is a collection of zero or more `geometry` or **geographyLineString** instances.</span></span>  
  
## <a name="multilinestring-instances"></a><span data-ttu-id="e458c-104">MultiLineString-Instanzen</span><span class="sxs-lookup"><span data-stu-id="e458c-104">MultiLineString instances</span></span>  
 <span data-ttu-id="e458c-105">Die nachfolgende Abbildung enthält Beispiele für `MultiLineString`-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="e458c-105">The illustration below shows examples of `MultiLineString` instances.</span></span>  
  
 <span data-ttu-id="e458c-106">![Beispiele für MultiLineString-Geometrieinstanzen](../../database-engine/media/multilinestring.gif "Beispiele für MultiLineString-Geometrieinstanzen")</span><span class="sxs-lookup"><span data-stu-id="e458c-106">![Examples of geometry MultiLineString instances](../../database-engine/media/multilinestring.gif "Examples of geometry MultiLineString instances")</span></span>  
  
 <span data-ttu-id="e458c-107">Folgendes wird dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e458c-107">As shown in the illustration:</span></span>  
  
-   <span data-ttu-id="e458c-108">Abbildung 1 zeigt eine einfache- `MultiLineString` Instanz, deren Grenze die vier Endpunkte der beiden `LineString` Elemente ist.</span><span class="sxs-lookup"><span data-stu-id="e458c-108">Figure 1 is a simple `MultiLineString` instance whose boundary is the four endpoints of its two `LineString` elements.</span></span>  
  
-   <span data-ttu-id="e458c-109">Abbildung 2 zeigt eine einfache `MultiLineString`-Instanz, da sich nur die Endpunkte der `LineString`-Elemente überschneiden.</span><span class="sxs-lookup"><span data-stu-id="e458c-109">Figure 2 is a simple `MultiLineString` instance because only the endpoints of the `LineString` elements intersect.</span></span> <span data-ttu-id="e458c-110">Die Begrenzung besteht aus den zwei nicht überlappenden Endpunkten.</span><span class="sxs-lookup"><span data-stu-id="e458c-110">The boundary is the two non-overlapping endpoints.</span></span>  
  
-   <span data-ttu-id="e458c-111">Abbildung 3 zeigt eine nicht einfache `MultiLineString`-Instanz, da der Innenbereich eines ihrer `LineString`-Elemente geschnitten wird.</span><span class="sxs-lookup"><span data-stu-id="e458c-111">Figure 3 is a nonsimple `MultiLineString` instance because the interior of one of its `LineString` elements is intersected.</span></span> <span data-ttu-id="e458c-112">Die Begrenzung dieser `MultiLineString`-Instanz besteht aus den vier Endpunkten.</span><span class="sxs-lookup"><span data-stu-id="e458c-112">The boundary of this `MultiLineString` instance is the four endpoints.</span></span>  
  
-   <span data-ttu-id="e458c-113">Abbildung 4 zeigt eine nicht einfache, nicht geschlossene `MultiLineString`-Instanz.</span><span class="sxs-lookup"><span data-stu-id="e458c-113">Figure 4 is a nonsimple, nonclosed `MultiLineString` instance.</span></span>  
  
-   <span data-ttu-id="e458c-114">Abbildung 5 zeigt eine einfache, nicht geschlossene `MultiLineString`-Instanz.</span><span class="sxs-lookup"><span data-stu-id="e458c-114">Figure 5 is a simple, nonclosed `MultiLineString`.</span></span> <span data-ttu-id="e458c-115">Er ist nicht geschlossen, da seine `LineStrings` Elemente nicht geschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="e458c-115">It is not closed because its `LineStrings` elements are not closed.</span></span> <span data-ttu-id="e458c-116">Sie ist einfach, da keiner der Innenbereiche der `LineStrings`-Instanzen sich mit anderen überschneidet.</span><span class="sxs-lookup"><span data-stu-id="e458c-116">It is simple because none of the interiors of any of the `LineStrings` instances intersect.</span></span>  
  
-   <span data-ttu-id="e458c-117">Abbildung 6 zeigt eine einfache, geschlossene `MultiLineString`-Instanz.</span><span class="sxs-lookup"><span data-stu-id="e458c-117">Figure 6 is a simple, closed `MultiLineString` instance.</span></span> <span data-ttu-id="e458c-118">Sie ist geschlossen, weil alle ihre Elemente geschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="e458c-118">It is closed because all its elements are closed.</span></span> <span data-ttu-id="e458c-119">Sie ist einfach, weil keines ihrer Elemente sich im Innenbereich mit anderen überschneidet.</span><span class="sxs-lookup"><span data-stu-id="e458c-119">It is simple because none of its elements intersect at the interiors.</span></span>  
  
### <a name="accepted-instances"></a><span data-ttu-id="e458c-120">Akzeptierte Instanzen</span><span class="sxs-lookup"><span data-stu-id="e458c-120">Accepted instances</span></span>  
 <span data-ttu-id="e458c-121">Damit eine `MultiLineString`-Instanz akzeptiert wird, muss sie entweder leer sein, oder sie darf nur aus `LineString` bestehen, die akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="e458c-121">For a `MultiLineString` instance to be accepted it must either be empty or comprised of only `LineString` intances that are accepted.</span></span> <span data-ttu-id="e458c-122">Weitere Informationen zu akzeptierten `LineString` Instanzen finden Sie unter [LineString](../spatial/linestring.md).</span><span class="sxs-lookup"><span data-stu-id="e458c-122">For more information on accepted `LineString` instances, see [LineString](../spatial/linestring.md).</span></span> <span data-ttu-id="e458c-123">In den folgenden Beispielen werden akzeptierte `MultiLineString`-Instanzen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e458c-123">The following are examples of accepted `MultiLineString` instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'MULTILINESTRING EMPTY';  
DECLARE @g2 geometry = 'MULTILINESTRING((1 1, 3 5), (-5 3, -8 -2))';  
DECLARE @g3 geometry = 'MULTILINESTRING((1 1, 5 5), (1 3, 3 1))';  
DECLARE @g4 geometry = 'MULTILINESTRING((1 1, 3 3, 5 5),(3 3, 5 5, 7 7))';  
```  
  
 <span data-ttu-id="e458c-124">Im folgenden Beispiel wird eine `System.FormatException` ausgelöst, da die zweite `LineString`-Instanz nicht gültig ist.</span><span class="sxs-lookup"><span data-stu-id="e458c-124">The following example throws a `System.FormatException` because the second `LineString` instance is not valid.</span></span>  
  
```  
DECLARE @g geometry = 'MULTILINESTRING((1 1, 3 5),(-5 3))';  
```  
  
### <a name="valid-instances"></a><span data-ttu-id="e458c-125">Gültige Instanzen</span><span class="sxs-lookup"><span data-stu-id="e458c-125">Valid instances</span></span>  
 <span data-ttu-id="e458c-126">Damit eine `MultiLineString`-Instanz gültig ist, muss sie die folgenden Kriterien erfüllen:</span><span class="sxs-lookup"><span data-stu-id="e458c-126">For a `MultiLineString` instance to be valid it must meet the following criteria:</span></span>  
  
1.  <span data-ttu-id="e458c-127">Alle Instanzen, die die `MultiLineString`-Instanz beinhalten, müssen gültige `LineString`-Instanzen sein.</span><span class="sxs-lookup"><span data-stu-id="e458c-127">All instances comprising the `MultiLineString` instance must be valid `LineString` instances.</span></span>  
  
2.  <span data-ttu-id="e458c-128">Zwei `LineString`-Instanzen, die die `MultiLineString`-Instanz beinhalten, dürfen sich nicht  im Verlauf eines Intervalls überlappen.</span><span class="sxs-lookup"><span data-stu-id="e458c-128">No two `LineString` instances comprising the `MultiLineString` instance may overlap over an interval.</span></span> <span data-ttu-id="e458c-129">Die `LineString`-Instanzen können sich nur mit einer endlichen Anzahl von Punkten überschneiden oder sich selbst oder andere `LineString`-Instanzen berühren.</span><span class="sxs-lookup"><span data-stu-id="e458c-129">The `LineString` instances can only intersect or touch themselves or other `LineString` instances at a finite number of points.</span></span>  
  
 <span data-ttu-id="e458c-130">Im folgenden Beispiel werden drei gültige `MultiLineString`-Instanzen und eine nicht gültige `MultiLineString`-Instanz gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e458c-130">The following example shows three valid `MultiLineString` instances and one `MultiLineString` instance that is not valid.</span></span>  
  
```  
DECLARE @g1 geometry = 'MULTILINESTRING EMPTY';  
DECLARE @g2 geometry = 'MULTILINESTRING((1 1, 3 5), (-5 3, -8 -2))';  
DECLARE @g3 geometry = 'MULTILINESTRING((1 1, 5 5), (1 3, 3 1))';  
DECLARE @g4 geometry = 'MULTILINESTRING((1 1, 3 3, 5 5),(3 3, 5 5, 7 7))';  
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();  
```  
  
 <span data-ttu-id="e458c-131">`@g4` ist nicht gültig, da die zweite `LineString`-Instanz die erste `LineString`-Instanz in einem Intervall überlappt.</span><span class="sxs-lookup"><span data-stu-id="e458c-131">`@g4` is not valid because the second `LineString` instance overlaps the first `LineString` instance at an interval.</span></span> <span data-ttu-id="e458c-132">Sie berühren sich mit einer unendlichen Anzahl von Punkten.</span><span class="sxs-lookup"><span data-stu-id="e458c-132">They touch at an infinite number of points.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e458c-133">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e458c-133">Examples</span></span>  
 <span data-ttu-id="e458c-134">Im folgenden Beispiel wird eine einfache `geometry``MultiLineString` -Instanz erstellt, die zwei `LineString` -Elemente mit der SRID 0 enthält.</span><span class="sxs-lookup"><span data-stu-id="e458c-134">The following example creates a simple `geometry``MultiLineString` instance containing two `LineString` elements with the SRID 0.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 2, 1 1), (1 0, 1 1))');  
```  
  
 <span data-ttu-id="e458c-135">Um diese Instanz mit einem anderen SRID zu instanziieren, verwenden Sie `STGeomFromText()` oder `STMLineStringFromText()`.</span><span class="sxs-lookup"><span data-stu-id="e458c-135">To instantiate this instance with a different SRID, use `STGeomFromText()` or `STMLineStringFromText()`.</span></span> <span data-ttu-id="e458c-136">Sie können auch `Parse()` verwenden und den SRID dann ändern, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e458c-136">You can also use `Parse()` and then modify the SRID, as shown in the following example.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('MULTILINESTRING((0 2, 1 1), (1 0, 1 1))');  
SET @g.STSrid = 13;  
```  
  
## <a name="see-also"></a><span data-ttu-id="e458c-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e458c-137">See Also</span></span>  
 <span data-ttu-id="e458c-138">[STLength &#40;geometry-Datentyp&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="e458c-138">[STLength &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stlength-geometry-data-type) </span></span>  
 <span data-ttu-id="e458c-139">[STIsClosed &#40;geometry-Datentyp&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="e458c-139">[STIsClosed &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stisclosed-geometry-data-type) </span></span>  
 <span data-ttu-id="e458c-140">[LineString](../spatial/linestring.md) </span><span class="sxs-lookup"><span data-stu-id="e458c-140">[LineString](../spatial/linestring.md) </span></span>  
 [<span data-ttu-id="e458c-141">Räumliche Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e458c-141">Spatial Data &#40;SQL Server&#41;</span></span>](../spatial/spatial-data-sql-server.md)  
  
  
