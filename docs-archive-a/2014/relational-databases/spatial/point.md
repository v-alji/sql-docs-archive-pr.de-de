---
title: Punkt | Microsoft-Dokumentation
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Point geometry subtype [SQL Server]
- geometry data type [SQL Server], spatial data
ms.assetid: 2a596ec4-8b2f-4962-bcb4-e5c8f77edad5
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 4b12069d84e00738e3ddac8c414f33903f4f0999
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621958"
---
# <a name="point"></a><span data-ttu-id="43f8d-102">Point</span><span class="sxs-lookup"><span data-stu-id="43f8d-102">Point</span></span>
  <span data-ttu-id="43f8d-103">In räumlichen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Daten ist ein `Point` ein nulldimensionales Objekt, das eine einzelne Position darstellt und einen Z-Wert (Höhe) und einen M-Wert (Maßeinheit) enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="43f8d-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spatial data, a `Point` is a 0-dimensional object representing a single location and may contain Z (elevation) and M (measure) values.</span></span>  
  
## <a name="geography-data-type"></a><span data-ttu-id="43f8d-104">geography-Datentyp</span><span class="sxs-lookup"><span data-stu-id="43f8d-104">Geography Data Type</span></span>  
 <span data-ttu-id="43f8d-105">Der Point-Typ für den geography-Datentyp stellt einen einzelnen Ort dar, wobei *Lat* für den Breitengrad und *Long* für den Längengrad steht.</span><span class="sxs-lookup"><span data-stu-id="43f8d-105">The Point type for the geography data type represents a single location where *Lat* represents latitude and *Long* represents longitude.</span></span> <span data-ttu-id="43f8d-106">Die Werte für die Breite und Länge werden in Grad gemessen.</span><span class="sxs-lookup"><span data-stu-id="43f8d-106">The values for latitude and longitude are measured in degrees.</span></span> <span data-ttu-id="43f8d-107">Die Werte für den Breitengrad liegen immer im Bereich [-90, 90], und eingegebene Werte, die außerhalb dieses Bereichs liegen, lösen eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="43f8d-107">Values for latitude always lie in the interval [-90, 90], and values that are inputted outside this range will throw an exception.</span></span> <span data-ttu-id="43f8d-108">Werte für den Längengrad liegen immer im Bereich [-180, 180], und eingegebene Werte, die außerhalb dieses Bereichs liegen, werden entsprechend angepasst.</span><span class="sxs-lookup"><span data-stu-id="43f8d-108">Values for longitude always lie in the interval (-180, 180], and values inputted outside this range are wrapped around to fit in this range.</span></span> <span data-ttu-id="43f8d-109">Wird etwa für den Längengrad der Wert 190 eingegeben, wird dieser Wert automatisch in den Wert -170 konvertiert.</span><span class="sxs-lookup"><span data-stu-id="43f8d-109">For example, if 190 is inputted for longitude, then it will be wrapped to the value -170.</span></span> <span data-ttu-id="43f8d-110">*SRID* stellt die SRID (Spatial Reference ID) der **geography** -Instanz dar, die Sie zurückgeben möchten.</span><span class="sxs-lookup"><span data-stu-id="43f8d-110">*SRID* represents the spatial reference ID of the **geography** instance that you wish to return.</span></span>  
  
## <a name="geometry-data-type"></a><span data-ttu-id="43f8d-111">geometry-Datentyp</span><span class="sxs-lookup"><span data-stu-id="43f8d-111">Geometry Data Type</span></span>  
 <span data-ttu-id="43f8d-112">Der Point-Typ für den geometry-Datentyp stellt einen einzelnen Ort dar, wobei *X* die X-Koordinate und *Y* die Y-Koordinate des generierten Punkts darstellt.</span><span class="sxs-lookup"><span data-stu-id="43f8d-112">The Point type for the geometry data type represents a single location where *X* represents the X-coordinate of the Point being generated and *Y* represents the Y-coordinate of the Point being generated.</span></span> <span data-ttu-id="43f8d-113">*SRID* stellt die SRID (Spatial Reference ID) der **geometry** -Instanz dar, die Sie zurückgeben möchten.</span><span class="sxs-lookup"><span data-stu-id="43f8d-113">*SRID* represents the spatial reference ID of the **geometry** instance that you wish to return.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="43f8d-114">Beispiele</span><span class="sxs-lookup"><span data-stu-id="43f8d-114">Examples</span></span>  
 <span data-ttu-id="43f8d-115">Im folgenden Beispiel wird eine einfache `geometry Point`-Instanz erstellt, die den Punkt (3, 4) mit dem SRID 0 darstellt.</span><span class="sxs-lookup"><span data-stu-id="43f8d-115">The following example creates a `geometry Point`instance representing the point (3, 4) with an SRID of 0.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('POINT (3 4)', 0);  
```  
  
 <span data-ttu-id="43f8d-116">Im nächsten Beispiel wird eine `geometry``Point` -Instanz erstellt, die den Punkt (3, 4) mit dem Z-Wert (Höhe) 7, dem M-Wert (Maßeinheit) 2,5 und dem Standard-SRID 0 darstellt.</span><span class="sxs-lookup"><span data-stu-id="43f8d-116">The next example creates a `geometry``Point` instance representing the point (3, 4) with a Z (elevation) value of 7, an M (measure) value of 2.5, and the default SRID of 0.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('POINT(3 4 7 2.5)');  
```  
  
 <span data-ttu-id="43f8d-117">Im abschließenden Beispiel werden die Werte X, Y, Z, und M für die `geometry``Point` -Instanz zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="43f8d-117">The final example returns the X, Y, Z, and M values for the `geometry``Point` instance.</span></span>  
  
```  
SELECT @g.STX;  
SELECT @g.STY;  
SELECT @g.Z;  
SELECT @g.M;  
```  
  
 <span data-ttu-id="43f8d-118">Z-Wert und M-Wert können explizit als NULL angegeben werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="43f8d-118">Z and M values may be explicitly specified as NULL, as shown in the following example.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::Parse('POINT(3 4 NULL NULL)');  
```  
  
## <a name="see-also"></a><span data-ttu-id="43f8d-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43f8d-119">See Also</span></span>  
 <span data-ttu-id="43f8d-120">[Multipoint](multipoint.md) </span><span class="sxs-lookup"><span data-stu-id="43f8d-120">[MultiPoint](multipoint.md) </span></span>  
 <span data-ttu-id="43f8d-121">[STX &#40;geometry-Datentyp&#41;](/sql/t-sql/spatial-geometry/stx-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="43f8d-121">[STX &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/stx-geometry-data-type) </span></span>  
 <span data-ttu-id="43f8d-122">[STY &#40;geometry-Datentyp&#41;](/sql/t-sql/spatial-geometry/sty-geometry-data-type) </span><span class="sxs-lookup"><span data-stu-id="43f8d-122">[STY &#40;geometry Data Type&#41;](/sql/t-sql/spatial-geometry/sty-geometry-data-type) </span></span>  
 [<span data-ttu-id="43f8d-123">Räumliche Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="43f8d-123">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
