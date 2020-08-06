---
title: Räumliche Daten (SQL Server) | Microsoft-Dokumentation
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- geography data type [SQL Server], spatial storage design
- planar spatial data [SQL Server], designing
- spatial data types [SQL Server]
- geodetic spatial data [SQL Server]
- geometry data type [SQL Server], spatial storage design
- spatial storage [SQL Server]
- geodetic spatial data [SQL Server], designing
ms.assetid: 41a132a1-09e2-4426-b9df-225270cb8e15
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 4d491420a9eca7c35b89b254a03381c6467c834c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621953"
---
# <a name="spatial-data-sql-server"></a><span data-ttu-id="bc032-102">Räumliche Daten (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="bc032-102">Spatial Data (SQL Server)</span></span>
  <span data-ttu-id="bc032-103">Räumliche Daten repräsentieren Daten zur physischen Position und Form geometrischer Objekte.</span><span class="sxs-lookup"><span data-stu-id="bc032-103">Spatial data represents information about the physical location and shape of geometric objects.</span></span> <span data-ttu-id="bc032-104">Diese Objekte können Punktpositionen oder komplexere Objekte wie Länder, Straßen oder Seen sein.</span><span class="sxs-lookup"><span data-stu-id="bc032-104">These objects can be point locations or more complex objects such as countries, roads, or lakes.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bc032-105">unterstützt zwei Typen von räumlichen Daten: den `geometry`-Datentyp und den `geography`-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="bc032-105">supports two spatial data types: the `geometry` data type and the `geography` data type.</span></span>  
  
-   <span data-ttu-id="bc032-106">Der `geometry`-Typ stellt Daten in einem euklidischen (flachen) Koordinatensystem dar.</span><span class="sxs-lookup"><span data-stu-id="bc032-106">The `geometry` type represents data in a Euclidean (flat) coordinate system.</span></span>  
  
-   <span data-ttu-id="bc032-107">Der `geography`-Typ stellt Daten in einem Erdkugel-Koordinatensystem dar.</span><span class="sxs-lookup"><span data-stu-id="bc032-107">The `geography` type represents data in a round-earth coordinate system.</span></span>  
  
 <span data-ttu-id="bc032-108">Beide Datentypen werden als .NET CLR (Common Language Runtime)-Datentypen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]implementiert.</span><span class="sxs-lookup"><span data-stu-id="bc032-108">Both data types are implemented as .NET common language runtime (CLR) data types in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bc032-109">Laden Sie für eine ausführliche Beschreibung und Beispiele der in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]eingeführten räumlichen Funktionen das Whitepaper [Neue räumliche Funktionen in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407)herunter.</span><span class="sxs-lookup"><span data-stu-id="bc032-109">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>  
  
##  <a name="related-tasks"></a><a name="reltasks"></a> <span data-ttu-id="bc032-110">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="bc032-110">Related Tasks</span></span>  
 [<span data-ttu-id="bc032-111">Erstellen, Aufbauen und Abfragen von geometry-Instanzen</span><span class="sxs-lookup"><span data-stu-id="bc032-111">Create, Construct, and Query geometry Instances</span></span>](create-construct-and-query-geometry-instances.md)  
 <span data-ttu-id="bc032-112">Beschreibt die Methoden, die mit Instanzen des geometry-Datentyps verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="bc032-112">Describes the methods that you can use with instances of the geometry data type.</span></span>  
  
 [<span data-ttu-id="bc032-113">Erstellen, Aufbauen und Abfragen von geography-Instanzen</span><span class="sxs-lookup"><span data-stu-id="bc032-113">Create, Construct, and Query geography Instances</span></span>](create-construct-and-query-geography-instances.md)  
 <span data-ttu-id="bc032-114">Beschreibt die Methoden, die mit Instanzen des geography-Datentyps verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="bc032-114">Describes the methods that you can use with instances of the geography data type.</span></span>  
  
 [<span data-ttu-id="bc032-115">Abfragen von nächsten Nachbarn aus räumlichen Daten</span><span class="sxs-lookup"><span data-stu-id="bc032-115">Query Spatial Data for Nearest Neighbor</span></span>](query-spatial-data-for-nearest-neighbor.md)  
 <span data-ttu-id="bc032-116">Beschreibt das allgemeine Abfragemuster, das zum Suchen der räumlichen Objekte, die einem bestimmten räumlichen Objekt am nächsten liegen, verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bc032-116">Describes the common query pattern that is used to find the closest spatial objects to a specific spatial object.</span></span>  
  
 [<span data-ttu-id="bc032-117">Erstellen, Ändern und Löschen von räumlichen Indizes</span><span class="sxs-lookup"><span data-stu-id="bc032-117">Create, Modify, and Drop Spatial Indexes</span></span>](create-modify-and-drop-spatial-indexes.md)  
 <span data-ttu-id="bc032-118">Stellt Informationen zum Erstellen, Ändern und Löschen eines räumlichen Indexes bereit.</span><span class="sxs-lookup"><span data-stu-id="bc032-118">Provides information about creating, altering, and dropping a spatial index.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="bc032-119">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="bc032-119">Related Content</span></span>  
 [<span data-ttu-id="bc032-120">Übersicht über räumliche Datentypen</span><span class="sxs-lookup"><span data-stu-id="bc032-120">Spatial Data Types Overview</span></span>](spatial-data-types-overview.md)  
 <span data-ttu-id="bc032-121">Bietet eine Einführung in die räumlichen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="bc032-121">Introduces the spatial data types.</span></span>  
  
-   [<span data-ttu-id="bc032-122">Point</span><span class="sxs-lookup"><span data-stu-id="bc032-122">Point</span></span>](point.md)  
  
-   [<span data-ttu-id="bc032-123">LineString</span><span class="sxs-lookup"><span data-stu-id="bc032-123">LineString</span></span>](linestring.md)  
  
-   [<span data-ttu-id="bc032-124">CircularString</span><span class="sxs-lookup"><span data-stu-id="bc032-124">CircularString</span></span>](circularstring.md)  
  
-   [<span data-ttu-id="bc032-125">CompoundCurve</span><span class="sxs-lookup"><span data-stu-id="bc032-125">CompoundCurve</span></span>](compoundcurve.md)  
  
-   [<span data-ttu-id="bc032-126">Polygon</span><span class="sxs-lookup"><span data-stu-id="bc032-126">Polygon</span></span>](polygon.md)  
  
-   [<span data-ttu-id="bc032-127">CurvePolygon</span><span class="sxs-lookup"><span data-stu-id="bc032-127">CurvePolygon</span></span>](curvepolygon.md)  
  
-   [<span data-ttu-id="bc032-128">MultiPoint</span><span class="sxs-lookup"><span data-stu-id="bc032-128">MultiPoint</span></span>](multipoint.md)  
  
-   [<span data-ttu-id="bc032-129">MultiLineString</span><span class="sxs-lookup"><span data-stu-id="bc032-129">MultiLineString</span></span>](multilinestring.md)  
  
-   [<span data-ttu-id="bc032-130">MultiPolygon</span><span class="sxs-lookup"><span data-stu-id="bc032-130">MultiPolygon</span></span>](multipolygon.md)  
  
-   [<span data-ttu-id="bc032-131">GeometryCollection</span><span class="sxs-lookup"><span data-stu-id="bc032-131">GeometryCollection</span></span>](geometrycollection.md)  
  
 [<span data-ttu-id="bc032-132">Übersicht über räumliche Indizes</span><span class="sxs-lookup"><span data-stu-id="bc032-132">Spatial Indexes Overview</span></span>](spatial-indexes-overview.md)  
 <span data-ttu-id="bc032-133">Bietet eine Einführung in räumliche Indizes und beschreibt Mosaik und Mosaikschemas.</span><span class="sxs-lookup"><span data-stu-id="bc032-133">Introduces spatial indexes and describes tessellation and tessellation schemes.</span></span>  
  
  
