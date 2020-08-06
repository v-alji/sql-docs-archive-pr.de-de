---
title: SRIDs (Spatial Reference Identifiers) | Microsoft Dokumentation
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Spatial Reference Identifiers (SRIDs)
- geodetic spatial data [SQL Server], identifiers
- SRID
ms.assetid: 0612658a-7d1b-4178-bdc2-42b914ea31a7
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 15db59b43731b9a39ff4bef78e3a6cb6929e9b47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619055"
---
# <a name="spatial-reference-identifiers-srids"></a><span data-ttu-id="90239-102">SRIDs (Spatial Reference Identifiers)</span><span class="sxs-lookup"><span data-stu-id="90239-102">Spatial Reference Identifiers (SRIDs)</span></span>
  <span data-ttu-id="90239-103">Jede räumliche Instanz hat einen SRID (Spatial Reference Identifier), einen räumlichen Referenzbezeichner.</span><span class="sxs-lookup"><span data-stu-id="90239-103">Each spatial instance has a spatial reference identifier (SRID).</span></span> <span data-ttu-id="90239-104">Der SRID bezieht sich auf ein räumliches Referenzsystem, das auf der jeweiligen Ellipsenform basiert, die für eine flache Erdabbildung oder runde Erdabbildung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="90239-104">The SRID corresponds to a spatial reference system based on the specific ellipsoid used for either flat-earth mapping or round-earth mapping.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="90239-105">Laden Sie für eine ausführliche Beschreibung und Beispiele der in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]eingeführten räumlichen Funktionen (einschließlich einer neuen SRID) das Whitepaper [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407)(in englischer Sprache) herunter.</span><span class="sxs-lookup"><span data-stu-id="90239-105">For a detailed description and examples of spatial features introduced in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], including a new SRID, download the white paper, [New Spatial Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=226407).</span></span>  
  
 <span data-ttu-id="90239-106">Eine räumliche Spalte kann Objekte mit unterschiedlichen SRIDs enthalten.</span><span class="sxs-lookup"><span data-stu-id="90239-106">A spatial column can contain objects with different SRIDs.</span></span> <span data-ttu-id="90239-107">Allerdings können nur räumliche Instanzen mit dem gleichen SRID verwendet werden, wenn Daten mit räumlichen Datenmethoden von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="90239-107">However, only spatial instances with the same SRID can be used when performing operations with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spatial data methods on your data.</span></span> <span data-ttu-id="90239-108">Das von zwei räumlichen Dateninstanzen abgeleitete Ergebnis einer beliebigen räumlichen Methode ist nur dann gültig, wenn diese Instanzen den gleichen SRID haben und die gleiche Maßeinheit, Bezugsebene und Projektion zur Bestimmung der Koordinaten der Instanzen verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="90239-108">The result of any spatial method derived from two spatial data instances is valid only if those instances have the same SRID that is based on the same unit of measurement, datum, and projection used to determine the coordinates of the instances.</span></span> <span data-ttu-id="90239-109">Die gängigsten Maßeinheiten für einen SRID sind Meter oder Quadratmeter.</span><span class="sxs-lookup"><span data-stu-id="90239-109">The most common units of measurement of a SRID are meters or square meters.</span></span>  
  
 <span data-ttu-id="90239-110">Wenn zwei räumliche Instanzen nicht über den gleichen SRID verfügen, dann geben mit diesen Instanzen verwendete Methoden des `geometry`- oder `geography`-Datentyps NULL zurück.</span><span class="sxs-lookup"><span data-stu-id="90239-110">If two spatial instances do not have the same SRID, the results from a `geometry` or `geography` Data Type method used on the instances will return NULL.</span></span> <span data-ttu-id="90239-111">Damit beispielsweise das folgende Prädikat ein Ergebnis ungleich NULL zurückgibt, müssen die beiden `geometry`-Instanzen `geometry1` und `geometry2` den gleichen SRID besitzen:</span><span class="sxs-lookup"><span data-stu-id="90239-111">For example, for the following predicate term to return a non-NULL result, the two `geometry` instances, `geometry1` and `geometry2`, must have the same SRID:</span></span>  
  
 `geometry1.STIntersects(geometry2) = 1`  
  
> [!NOTE]  
>  <span data-ttu-id="90239-112">Das Spatial Reference Identification-System wird durch den [European Petroleum Survey Group-Standard (EPSG)](https://go.microsoft.com/fwlink/?LinkId=99349) definiert. Hierbei handelt es sich um einen für die Kartografie, Landvermessung und Speicherung geodätischer Daten entwickelten Satz von Standards.</span><span class="sxs-lookup"><span data-stu-id="90239-112">The spatial reference identification system is defined by the [European Petroleum Survey Group (EPSG)](https://go.microsoft.com/fwlink/?LinkId=99349) standard, which is a set of standards developed for cartography, surveying, and geodetic data storage.</span></span> <span data-ttu-id="90239-113">Dieser Standard ist Eigentum des Oil and Gas Producers (OGP) Surveying and Positioning Committee.</span><span class="sxs-lookup"><span data-stu-id="90239-113">This standard is owned by the Oil and Gas Producers (OGP) Surveying and Positioning Committee.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90239-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90239-114">See Also</span></span>  
 [<span data-ttu-id="90239-115">Übersicht über räumliche Datentypen</span><span class="sxs-lookup"><span data-stu-id="90239-115">Spatial Data Types Overview</span></span>](spatial-data-types-overview.md)  
  
  
