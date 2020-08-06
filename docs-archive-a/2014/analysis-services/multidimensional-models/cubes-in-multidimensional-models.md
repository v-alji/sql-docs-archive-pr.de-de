---
title: Cubes in mehrdimensionalen Modellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- OLAP objects [Analysis Services], cubes
- cubes [Analysis Services], about cubes
- cubes [Analysis Services]
- OLAP [Analysis Services], cubes
ms.assetid: e0f7acf3-4b07-41fc-a5fc-ac30b4a56c54
author: minewiskan
ms.author: owend
ms.openlocfilehash: 372bb8075b232ff8fbf8a54facf9bc065e6763a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725098"
---
# <a name="cubes-in-multidimensional-models"></a><span data-ttu-id="b3c75-102">Cubes in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="b3c75-102">Cubes in Multidimensional Models</span></span>
  <span data-ttu-id="b3c75-103">Ein Cube ist eine mehrdimensionale Struktur, die Informationen für analytische Zwecke enthält. Die Hauptbestandteile eines Cubes sind Dimensionen und Measures.</span><span class="sxs-lookup"><span data-stu-id="b3c75-103">A cube is a multidimensional structure that contains information for analytical purposes; the main constituents of a cube are dimensions and measures.</span></span> <span data-ttu-id="b3c75-104">Dimensionen definieren die Struktur des Cubes, den Sie für Aufteilungen verwenden, während Measures dem Endbenutzer numerische Werte zur Verfügung stellen, die für ihn von Interesse sind.</span><span class="sxs-lookup"><span data-stu-id="b3c75-104">Dimensions define the structure of the cube that you use to slice and dice over, and measures provide aggregated numerical values of interest to the end user.</span></span> <span data-ttu-id="b3c75-105">Als logische Struktur ermöglicht ein Cube einer Clientanwendung das Abrufen von Werten von Measures, so als ob sie in Zellen im Cube enthalten wären. Zellen werden für jeden möglichen zusammengefassten Wert definiert.</span><span class="sxs-lookup"><span data-stu-id="b3c75-105">As a logical structure, a cube allows a client application to retrieve values, of measures, as if they were contained in cells in the cube; cells are defined for every possible summarized value.</span></span> <span data-ttu-id="b3c75-106">Eine Zelle im Cube wird von der Schnittmenge von Dimensionselementen definiert und enthält die aggregierten Werte der Measures an dieser speziellen Schnittmenge.</span><span class="sxs-lookup"><span data-stu-id="b3c75-106">A cell, in the cube, is defined by the intersection of dimension members and contains the aggregated values of the measures at that specific intersection.</span></span>  
  
## <a name="benefits-of-using-cubes"></a><span data-ttu-id="b3c75-107">Vorteile der Verwendung von Cubes</span><span class="sxs-lookup"><span data-stu-id="b3c75-107">Benefits of Using Cubes</span></span>  
 <span data-ttu-id="b3c75-108">Ein Cube bietet eine einzelne Position, an der alle verknüpften Daten für die Analyse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="b3c75-108">A cube provides a single place where all related data, for analysis, is stored.</span></span>  
  
## <a name="components-of-cubes"></a><span data-ttu-id="b3c75-109">Komponenten von Cubes</span><span class="sxs-lookup"><span data-stu-id="b3c75-109">Components of Cubes</span></span>  
 <span data-ttu-id="b3c75-110">Ein Cube besteht aus den folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="b3c75-110">A cube is composed of:</span></span>  
  
|<span data-ttu-id="b3c75-111">Element</span><span class="sxs-lookup"><span data-stu-id="b3c75-111">Element</span></span>|<span data-ttu-id="b3c75-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b3c75-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b3c75-113">Dimensionen</span><span class="sxs-lookup"><span data-stu-id="b3c75-113">Dimensions</span></span>|[<span data-ttu-id="b3c75-114">Dimensionen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="b3c75-114">Dimensions in Multidimensional Models</span></span>](dimensions-in-multidimensional-models.md)|  
|<span data-ttu-id="b3c75-115">Measures und Measuregruppen</span><span class="sxs-lookup"><span data-stu-id="b3c75-115">Measures and Measure Groups</span></span>|[<span data-ttu-id="b3c75-116">Erstellen von Measures und Measuregruppen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="b3c75-116">Create Measures and Measure Groups in Multidimensional Models</span></span>](create-measures-and-measure-groups-in-multidimensional-models.md)|  
|<span data-ttu-id="b3c75-117">Partitionen</span><span class="sxs-lookup"><span data-stu-id="b3c75-117">Partitions</span></span>|[<span data-ttu-id="b3c75-118">Partitionen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="b3c75-118">Partitions in Multidimensional Models</span></span>](partitions-in-multidimensional-models.md)|  
|<span data-ttu-id="b3c75-119">Perspektiven</span><span class="sxs-lookup"><span data-stu-id="b3c75-119">Perspectives</span></span>|[<span data-ttu-id="b3c75-120">Perspektiven in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="b3c75-120">Perspectives in Multidimensional Models</span></span>](perspectives-in-multidimensional-models.md)|  
|<span data-ttu-id="b3c75-121">Hierarchien</span><span class="sxs-lookup"><span data-stu-id="b3c75-121">Hierarchies</span></span>|[<span data-ttu-id="b3c75-122">Erstellen von benutzerdefinierten Hierarchien</span><span class="sxs-lookup"><span data-stu-id="b3c75-122">Create User-Defined Hierarchies</span></span>](user-defined-hierarchies-create.md)|  
|<span data-ttu-id="b3c75-123">Aktionen</span><span class="sxs-lookup"><span data-stu-id="b3c75-123">Actions</span></span>|[<span data-ttu-id="b3c75-124">Aktionen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="b3c75-124">Actions in Multidimensional Models</span></span>](actions-in-multidimensional-models.md)|  
|<span data-ttu-id="b3c75-125">Key Performance Indicators (KPI)</span><span class="sxs-lookup"><span data-stu-id="b3c75-125">Key Performance Indicators (KPI)</span></span>|[<span data-ttu-id="b3c75-126">Leistungskennzahlen &#40;Key Performance Indicators, KPIs&#41; in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="b3c75-126">Key Performance Indicators &#40;KPIs&#41; in Multidimensional Models</span></span>](key-performance-indicators-kpis-in-multidimensional-models.md)|  
|<span data-ttu-id="b3c75-127">Berechnungen</span><span class="sxs-lookup"><span data-stu-id="b3c75-127">Calculations</span></span>|[<span data-ttu-id="b3c75-128">Berechnungen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="b3c75-128">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)|  
|<span data-ttu-id="b3c75-129">Translations</span><span class="sxs-lookup"><span data-stu-id="b3c75-129">Translations</span></span>|[<span data-ttu-id="b3c75-130">Übersetzungen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="b3c75-130">Translations in Multidimensional Models</span></span>](translations-in-multidimensional-models-analysis-services.md)|  
  
## <a name="related-tasks"></a><span data-ttu-id="b3c75-131">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="b3c75-131">Related Tasks</span></span>  
  
|<span data-ttu-id="b3c75-132">Thema</span><span class="sxs-lookup"><span data-stu-id="b3c75-132">Topic</span></span>|<span data-ttu-id="b3c75-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3c75-133">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="b3c75-134">Erstellen eines Cubes mit dem Cube-Assistenten</span><span class="sxs-lookup"><span data-stu-id="b3c75-134">Create a Cube Using the Cube Wizard</span></span>](create-a-cube-using-the-cube-wizard.md)|<span data-ttu-id="b3c75-135">Beschreibt das Definieren von Cubes, Dimensionen, Dimensionsattributen und benutzerdefinierten Hierarchien mithilfe des Cube-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="b3c75-135">Describes how to use the Cube Wizard to define a cube, dimensions, dimension attributes, and user-defined hierarchies.</span></span>|  
|[<span data-ttu-id="b3c75-136">Erstellen von Measures und Measuregruppen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="b3c75-136">Create Measures and Measure Groups in Multidimensional Models</span></span>](create-measures-and-measure-groups-in-multidimensional-models.md)|<span data-ttu-id="b3c75-137">Beschreibt das Definieren von Measuregruppen.</span><span class="sxs-lookup"><span data-stu-id="b3c75-137">Describes how to define measure groups.</span></span>|  
|[<span data-ttu-id="b3c75-138">Berechnungen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="b3c75-138">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)|<span data-ttu-id="b3c75-139">Beschreibt das Definieren und Konfigurieren einer Berechnung in einem MDX-Skript.</span><span class="sxs-lookup"><span data-stu-id="b3c75-139">Describes how to define and configure a calculation in an MDX script.</span></span>|  
|[<span data-ttu-id="b3c75-140">Aktionen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="b3c75-140">Actions in Multidimensional Models</span></span>](actions-in-multidimensional-models.md)|<span data-ttu-id="b3c75-141">Beschreibt das Definieren und Konfigurieren einer Aktion.</span><span class="sxs-lookup"><span data-stu-id="b3c75-141">Describes how to define and configure an action.</span></span>|  
|[<span data-ttu-id="b3c75-142">Perspektiven in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="b3c75-142">Perspectives in Multidimensional Models</span></span>](perspectives-in-multidimensional-models.md)|<span data-ttu-id="b3c75-143">Beschreibt das Definieren und Konfigurieren einer Perspektive.</span><span class="sxs-lookup"><span data-stu-id="b3c75-143">Describes how to define and configure a perspective.</span></span>|  
|[<span data-ttu-id="b3c75-144">Definieren von gespeicherten Proze</span><span class="sxs-lookup"><span data-stu-id="b3c75-144">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)|<span data-ttu-id="b3c75-145">Beschreibt das Verwenden von gespeicherten Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="b3c75-145">Describes how to work with stored procedures.</span></span>|  
  
  
