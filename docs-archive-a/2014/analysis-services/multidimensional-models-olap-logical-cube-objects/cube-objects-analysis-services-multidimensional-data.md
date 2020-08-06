---
title: Cubeobjekte (Analysis Services Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- cubes [Analysis Services], objects
ms.assetid: 5cee362e-3f95-4467-bc6c-29b1518ecbf3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0e6dfb75be696ab26893e668b99dc36c7340f86c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618941"
---
# <a name="cube-objects-analysis-services---multidimensional-data"></a><span data-ttu-id="ffc79-102">Cubeobjekte (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="ffc79-102">Cube Objects (Analysis Services - Multidimensional Data)</span></span>
    
## <a name="introducing-cube-objects"></a><span data-ttu-id="ffc79-103">Einführung in Cubeobjekte</span><span class="sxs-lookup"><span data-stu-id="ffc79-103">Introducing Cube Objects</span></span>  
 <span data-ttu-id="ffc79-104">Ein einfaches <xref:Microsoft.AnalysisServices.Cube>-Objekt besteht aus grundlegenden Informationen, Dimensionen und Measuregruppen.</span><span class="sxs-lookup"><span data-stu-id="ffc79-104">A simple <xref:Microsoft.AnalysisServices.Cube> object is composed of: basic information, dimensions, and measure groups.</span></span> <span data-ttu-id="ffc79-105">Grundlegende Informationen beinhalten den Namen des Cubes, das Standardmeasure des Cubes, die Datenquelle, den Speichermodus usw.</span><span class="sxs-lookup"><span data-stu-id="ffc79-105">Basic information includes the name of the cube, the default measure of the cube, the data source, the storage mode, and others.</span></span>  
  
 <span data-ttu-id="ffc79-106">Die Dimensionsauflistung enthält den eigentlichen Dimensionssatz, der im Cube aus der Dimensionsauflistung der Datenbank verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ffc79-106">The Dimensions collection contains the actual set of dimensions used in the cube from the database dimensions colection.</span></span> <span data-ttu-id="ffc79-107">Alle Dimensionen müssen in der Dimensionsauflistung der Datenbank definiert werden, bevor im Cube auf sie verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ffc79-107">All dimensions have to be defined in the dimensions collection of the database before being referenced in the cube.</span></span> <span data-ttu-id="ffc79-108">Private Dimensionen sind in nicht verfügbar [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ffc79-108">Private dimensions are not available in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="ffc79-109">Measuregruppen sind Sätze von Measures im Cube.</span><span class="sxs-lookup"><span data-stu-id="ffc79-109">Measure groups are sets of measures in the cube.</span></span> <span data-ttu-id="ffc79-110">Eine Measuregruppe ist eine Auflistung von Measures, die eine gemeinsame Datenquellensicht und einen gemeinsamen Satz von Dimensionen besitzen.</span><span class="sxs-lookup"><span data-stu-id="ffc79-110">A measure group is a collection of measures that have a common data source view and a common set of dimensions.</span></span> <span data-ttu-id="ffc79-111">Eine Measuregruppe ist die Verarbeitungseinheit für Measures. Measuregruppen können einzeln verarbeitet und dann durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="ffc79-111">A measure group is the unit of process for measures; measure groups can be processed individually and then browsed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ffc79-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ffc79-112">In this section</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ffc79-113">Thema</span><span class="sxs-lookup"><span data-stu-id="ffc79-113">Topic</span></span>||  
|[<span data-ttu-id="ffc79-114">Aktionen &#40;Analysis Services – mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="ffc79-114">Actions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../multidimensional-models/actions-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="ffc79-115">Aggregations and Aggregation Designs</span><span class="sxs-lookup"><span data-stu-id="ffc79-115">Aggregations and Aggregation Designs</span></span>](aggregations-and-aggregation-designs.md)||  
|[<span data-ttu-id="ffc79-116">Berechnungen</span><span class="sxs-lookup"><span data-stu-id="ffc79-116">Calculations</span></span>](calculations.md)||  
|[<span data-ttu-id="ffc79-117">Cubezellen &#40;Analysis Services-Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="ffc79-117">Cube Cells &#40;Analysis Services - Multidimensional Data&#41;</span></span>](cube-cells-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="ffc79-118">Cubeeigenschaften</span><span class="sxs-lookup"><span data-stu-id="ffc79-118">Cube Properties</span></span>](cube-properties-multidimensional-model-programming.md)||  
|[<span data-ttu-id="ffc79-119">Cube-Speicher &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="ffc79-119">Cube Storage &#40;Analysis Services - Multidimensional Data&#41;</span></span>](cube-storage-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="ffc79-120">Cubeübersetzungen</span><span class="sxs-lookup"><span data-stu-id="ffc79-120">Cube Translations</span></span>](cube-translations.md)||  
|[<span data-ttu-id="ffc79-121">Dimensionsbeziehungen</span><span class="sxs-lookup"><span data-stu-id="ffc79-121">Dimension Relationships</span></span>](dimension-relationships.md)||  
|[<span data-ttu-id="ffc79-122">Leistungskennzahlen &#40;Key Performance Indicators, KPIs&#41; in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="ffc79-122">Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models</span></span>](../multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md)||  
|[<span data-ttu-id="ffc79-123">Measures und Measuregruppen</span><span class="sxs-lookup"><span data-stu-id="ffc79-123">Measures and Measure Groups</span></span>](../multidimensional-models/measures-and-measure-groups.md)||  
|[<span data-ttu-id="ffc79-124">Partitionen &#40;Analysis Services – mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="ffc79-124">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](partitions-analysis-services-multidimensional-data.md)||  
|[<span data-ttu-id="ffc79-125">Perspektiven</span><span class="sxs-lookup"><span data-stu-id="ffc79-125">Perspectives</span></span>](perspectives.md)||  
  
  
