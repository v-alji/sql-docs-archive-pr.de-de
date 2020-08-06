---
title: MultiPoint | Microsoft-Dokumentation
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- MultiPoint geometry subtype [SQL Server]
ms.assetid: 2aaab211-3aba-4dbd-90b7-095d997b1f62
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: b741071b7986aceea4e49d4fde8293ef2c96fc2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621962"
---
# <a name="multipoint"></a><span data-ttu-id="b68b5-102">MultiPoint</span><span class="sxs-lookup"><span data-stu-id="b68b5-102">MultiPoint</span></span>
  <span data-ttu-id="b68b5-103">Ein `MultiPoint` ist eine Auflistung von null oder mehr Punkten.</span><span class="sxs-lookup"><span data-stu-id="b68b5-103">A `MultiPoint` is a collection of zero or more points.</span></span> <span data-ttu-id="b68b5-104">Die Begrenzung einer `MultiPoint`-Instanz ist leer.</span><span class="sxs-lookup"><span data-stu-id="b68b5-104">The boundary of a `MultiPoint` instance is empty.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b68b5-105">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b68b5-105">Examples</span></span>  
 <span data-ttu-id="b68b5-106">Im folgenden Beispiel wird eine `geometry MultiPoint` -Instanz mit dem SRID 23 und zwei Punkten erstellt: ein Punkt mit den Koordinaten (2, 3), ein Punkt mit den Koordinaten (7, 8) und ein Z-Wert von 9,5.</span><span class="sxs-lookup"><span data-stu-id="b68b5-106">The following example creates a `geometry MultiPoint` instance with SRID 23 and two points: one point with the coordinates (2, 3), one point with the coordinates (7, 8), and a Z value of 9.5.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('MULTIPOINT((2 3), (7 8 9.5))', 23);  
```  
  
 <span data-ttu-id="b68b5-107">Diese `MultiPoint` -Instanz kann auch mit `STMPointFromText()` ausgedrückt werden, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b68b5-107">This `MultiPoint` instance can also be expressed using `STMPointFromText()` as shown below.</span></span>  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STMPointFromText('MULTIPOINT((2 3), (7 8 9.5))', 23);  
```  
  
 <span data-ttu-id="b68b5-108">Im folgenden Beispiel wird mit der Methode `STGeometryN()` eine Beschreibung des ersten Punkts der Auflistung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="b68b5-108">The following example uses the method `STGeometryN()` to retrieve a description of the first point in the collection.</span></span>  
  
```  
SELECT @g.STGeometryN(1).STAsText();  
```  
  
## <a name="see-also"></a><span data-ttu-id="b68b5-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b68b5-109">See Also</span></span>  
 <span data-ttu-id="b68b5-110">[Punkt](point.md) </span><span class="sxs-lookup"><span data-stu-id="b68b5-110">[Point](point.md) </span></span>  
 [<span data-ttu-id="b68b5-111">Räumliche Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b68b5-111">Spatial Data &#40;SQL Server&#41;</span></span>](spatial-data-sql-server.md)  
  
  
