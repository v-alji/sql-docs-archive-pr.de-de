---
title: Dimensionen (Analysis Services Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- OLAP objects [Analysis Services], dimensions
- dimensions [Analysis Services]
- Analysis Services objects, dimensions
ms.assetid: 2b114135-2572-4479-8c81-3ccf0cfeb9f7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e0e15d4f74c2c6cec06edaf692199e48534c7e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723197"
---
# <a name="dimensions-analysis-services---multidimensional-data"></a><span data-ttu-id="44ea4-102">Dimensionen (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="44ea4-102">Dimensions (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="44ea4-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] sind Dimensionen eine grundlegende Komponente von Cubes.</span><span class="sxs-lookup"><span data-stu-id="44ea4-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], dimensions are a fundamental component of cubes.</span></span> <span data-ttu-id="44ea4-104">Mit Dimensionen werden Daten nach Interessensbereichen geordnet, z. B. nach Kunden, Geschäften oder Angestellten.</span><span class="sxs-lookup"><span data-stu-id="44ea4-104">Dimensions organize data with relation to an area of interest, such as customers, stores, or employees, to users.</span></span> <span data-ttu-id="44ea4-105">Dimensionen in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] enthalten Attribute, die den Spalten in den Dimensionstabellen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="44ea4-105">Dimensions in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] contain attributes that correspond to columns in dimension tables.</span></span> <span data-ttu-id="44ea4-106">Diese Attribute erscheinen in der Form von Attributhierarchien und können in benutzerdefinierten Hierarchien organisiert, oder basierend auf den Spalten der zugrunde liegenden Dimensionstabelle als Über-/Unterordnungshierarchien definiert werden.</span><span class="sxs-lookup"><span data-stu-id="44ea4-106">These attributes appear as attribute hierarchies and can be organized into user-defined hierarchies, or can be defined as parent-child hierarchies based on columns in the underlying dimension table.</span></span> <span data-ttu-id="44ea4-107">Hierarchien werden dazu verwendet, die in einem Cube enthaltenen Measures zu ordnen.</span><span class="sxs-lookup"><span data-stu-id="44ea4-107">Hierarchies are used to organize measures that are contained in a cube.</span></span> <span data-ttu-id="44ea4-108">Die folgenden Themen bieten eine Übersicht über Dimensionen, Attribute und Hierarchien.</span><span class="sxs-lookup"><span data-stu-id="44ea4-108">The following topics provide an overview of dimensions, attributes, and hierarchies.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="44ea4-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="44ea4-109">In This Section</span></span>  
  
|<span data-ttu-id="44ea4-110">Thema</span><span class="sxs-lookup"><span data-stu-id="44ea4-110">Topic</span></span>|<span data-ttu-id="44ea4-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="44ea4-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="44ea4-112">Einführung in Dimensionen &#40;Analysis Services – mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="44ea4-112">Introduction to Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimensions-analysis-services-multidimensional-data.md)|<span data-ttu-id="44ea4-113">Bietet eine Übersicht über die Konzepte von Dimensionen.</span><span class="sxs-lookup"><span data-stu-id="44ea4-113">Provides an overview of dimension concepts.</span></span>|  
|[<span data-ttu-id="44ea4-114">Attribute und Attributhierarchien</span><span class="sxs-lookup"><span data-stu-id="44ea4-114">Attributes and Attribute Hierarchies</span></span>](attributes-and-attribute-hierarchies.md)|<span data-ttu-id="44ea4-115">Beschreibt Attribute und Attributhierarchien.</span><span class="sxs-lookup"><span data-stu-id="44ea4-115">Describes attributes and attribute hierarchies.</span></span>|  
|[<span data-ttu-id="44ea4-116">Benutzerhierarchien</span><span class="sxs-lookup"><span data-stu-id="44ea4-116">User Hierarchies</span></span>](user-hierarchies.md)|<span data-ttu-id="44ea4-117">Beschreibt benutzerdefinierte Attributhierarchien.</span><span class="sxs-lookup"><span data-stu-id="44ea4-117">Describes user-defined hierarchies of attributes.</span></span>|  
|[<span data-ttu-id="44ea4-118">Dimensionen mit aktiviertem Schreibzugriff</span><span class="sxs-lookup"><span data-stu-id="44ea4-118">Write-Enabled Dimensions</span></span>](write-enabled-dimensions.md)|<span data-ttu-id="44ea4-119">Beschreibt Dimensionen mit aktiviertem Schreibzugriff.</span><span class="sxs-lookup"><span data-stu-id="44ea4-119">Describes write-enabled dimensions.</span></span>|  
|[<span data-ttu-id="44ea4-120">Dimensionsübersetzungen</span><span class="sxs-lookup"><span data-stu-id="44ea4-120">Dimension Translations</span></span>](dimension-translations.md)|<span data-ttu-id="44ea4-121">Beschreibt Übersetzungen von Dimensionsmetadaten.</span><span class="sxs-lookup"><span data-stu-id="44ea4-121">Describes translations of dimension meta data.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44ea4-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="44ea4-122">See Also</span></span>  
 <span data-ttu-id="44ea4-123">[Dimensionen in mehrdimensionalen Modellen](../multidimensional-models/dimensions-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="44ea4-123">[Dimensions in Multidimensional Models](../multidimensional-models/dimensions-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="44ea4-124">Cubeobjekte &#40;Analysis Services Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="44ea4-124">Cube Objects &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md)  
  
  
