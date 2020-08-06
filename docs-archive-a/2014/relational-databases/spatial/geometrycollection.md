---
title: GeometryCollection | Microsoft-Dokumentation
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- GeomCollection geometry subtype [SQL Server]
- geometry subtypes [SQL Server]
ms.assetid: 4445c0d9-a66b-4d7c-88e4-a66fa6f7d9fd
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 71d2234a9b73b7647554e364fe3864f089a47a0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621975"
---
# <a name="geometrycollection"></a><span data-ttu-id="77e70-102">GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="77e70-102">GeometryCollection</span></span>
  <span data-ttu-id="77e70-103">Ein `GeometryCollection`-Objekt ist eine Auflistung von null oder mehr `geometry`- oder `geography`-Instanzen.</span><span class="sxs-lookup"><span data-stu-id="77e70-103">A `GeometryCollection` is a collection of zero or more `geometry` or `geography` instances.</span></span> <span data-ttu-id="77e70-104">Eine `GeometryCollection` kann leer sein.</span><span class="sxs-lookup"><span data-stu-id="77e70-104">A `GeometryCollection` can be empty.</span></span>  
  
## <a name="geometrycollection-instances"></a><span data-ttu-id="77e70-105">GeometryCollection-Instanzen</span><span class="sxs-lookup"><span data-stu-id="77e70-105">GeometryCollection Instances</span></span>  
  
### <a name="accepted-instances"></a><span data-ttu-id="77e70-106">Akzeptierte Instanzen</span><span class="sxs-lookup"><span data-stu-id="77e70-106">Accepted Instances</span></span>  
 <span data-ttu-id="77e70-107">Damit eine `GeometryCollection`-Instanz akzeptiert wird, muss es sich um eine leere `GeometryCollection`-Instanz handeln, oder alle Instanzen, die die `GeometryCollection` beinhalten, müssen akzeptierte Instanzen sein.</span><span class="sxs-lookup"><span data-stu-id="77e70-107">For a `GeometryCollection` instance to be accepted, it must either be an empty `GeometryCollection` instance or all the instances comprising the `GeometryCollection` instance must be accepted instances.</span></span> <span data-ttu-id="77e70-108">Im folgenden Beispiel werden akzeptierte Instanzen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="77e70-108">The following example shows accepted instances.</span></span>  
  
```  
DECLARE @g1 geometry = 'GEOMETRYCOLLECTION EMPTY';  
DECLARE @g2 geometry = 'GEOMETRYCOLLECTION(LINESTRING EMPTY,POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g3 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
```  
  
 <span data-ttu-id="77e70-109">Im folgenden Beispiel wird eine `System.FormatException` ausgelöst, da die `LinesString`-Instanz in der `GeometryCollection`-Instanz nicht akzeptiert wird.</span><span class="sxs-lookup"><span data-stu-id="77e70-109">The following example throws a `System.FormatException` because the `LinesString` instance in the `GeometryCollection` instance is not accepted.</span></span>  
  
```  
DECLARE @g geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1), POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
```  
  
### <a name="valid-instances"></a><span data-ttu-id="77e70-110">Gültige Instanzen</span><span class="sxs-lookup"><span data-stu-id="77e70-110">Valid Instances</span></span>  
 <span data-ttu-id="77e70-111">Eine `GeometryCollection`-Instanz ist gültig, wenn alle Instanzen, die die `GeometryCollection`-Instanz beinhalten, gültig sind.</span><span class="sxs-lookup"><span data-stu-id="77e70-111">A `GeometryCollection` instance is valid when all instances that comprise the `GeometryCollection` instance are valid.</span></span> <span data-ttu-id="77e70-112">Im folgenden Beispiel werden drei gültige `GeometryCollection`-Instanzen und eine nicht gültige Instanz gezeigt.</span><span class="sxs-lookup"><span data-stu-id="77e70-112">The following shows three valid `GeometryCollection` instances and one instance that is not valid.</span></span>  
  
```  
DECLARE @g1 geometry = 'GEOMETRYCOLLECTION EMPTY';  
DECLARE @g2 geometry = 'GEOMETRYCOLLECTION(LINESTRING EMPTY,POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g3 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, -1 -5, -5 -5, -5 -1, -1 -1)))';  
DECLARE @g4 geometry = 'GEOMETRYCOLLECTION(LINESTRING(1 1, 3 5),POLYGON((-1 -1, 1 -5, -5 5, -5 -1, -1 -1)))';  
SELECT @g1.STIsValid(), @g2.STIsValid(), @g3.STIsValid(), @g4.STIsValid();  
```  
  
 <span data-ttu-id="77e70-113">`@g4` ist nicht gültig, da die `Polygon`-Instanz in der `GeometryCollection`-Instanz nicht gültig ist.</span><span class="sxs-lookup"><span data-stu-id="77e70-113">`@g4` is not valid because the `Polygon` instance in the `GeometryCollection` instance is not valid.</span></span>  
  
 <span data-ttu-id="77e70-114">Weitere Informationen über akzeptierte und gültige Instanzen finden Sie unter [Point](point.md), [MultiPoint](multipoint.md), [LineString](linestring.md), [MultiLineString](multilinestring.md), [Polygon](polygon.md)und [MultiPolygon](multipolygon.md).</span><span class="sxs-lookup"><span data-stu-id="77e70-114">For more information on accepted and valid instances, see [Point](point.md), [MultiPoint](multipoint.md), [LineString](linestring.md), [MultiLineString](multilinestring.md), [Polygon](polygon.md), and [MultiPolygon](multipolygon.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="77e70-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="77e70-115">Examples</span></span>  
 <span data-ttu-id="77e70-116">Im folgenden Beispiel wird eine `geometry``GeometryCollection` mit Z-Werten im SRID 1 instanziiert, der eine `Point` -Instanz und eine `Polygon` -Instanz enthält.</span><span class="sxs-lookup"><span data-stu-id="77e70-116">The following example instantiates a `geometry``GeometryCollection` with Z values in SRID 1 containing a `Point` instance and a `Polygon` instance.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomCollFromText('GEOMETRYCOLLECTION(POINT(3 3 1), POLYGON((0 0 2, 1 10 3, 1 0 4, 0 0 2)))', 1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="77e70-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="77e70-117">See Also</span></span>  
 [<span data-ttu-id="77e70-118">Räumliche Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="77e70-118">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
