---
title: Datenbankobjekte (Analysis Services Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- objects [Analysis Services], about objects
- SQL Server Analysis Services, objects
- Analysis Services objects, about Analysis Services objects
- SSAS, objects
- Analysis Services objects
- objects [Analysis Services]
ms.assetid: f76d869b-fc1d-4807-9f28-da09c7be382d
author: minewiskan
ms.author: owend
ms.openlocfilehash: d61e3213356146e1cf9e452e0b62e02c96bd4902
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727246"
---
# <a name="database-objects-analysis-services---multidimensional-data"></a><span data-ttu-id="5e4e0-102">Datenbankobjekte (Analysis Services - Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="5e4e0-102">Database Objects (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="5e4e0-103">Eine [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] -Instanz enthält Datenbankobjekte und Assemblys für die Verwendung mit OLAP (Online Analytical Processing) und Data Mining.</span><span class="sxs-lookup"><span data-stu-id="5e4e0-103">A [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] instance contains database objects and assemblies for use with online analytical processing (OLAP) and data mining.</span></span>  
  
-   <span data-ttu-id="5e4e0-104">Datenbanken enthalten OLAP- und Data Mining-Objekte, z.&#160;B. Datenquellen, Datenquellensichten, Cubes, Measures, Measuregruppen, Dimensionen, Attribute, Hierarchien, Miningstrukturen, Miningmodelle und Rollen.</span><span class="sxs-lookup"><span data-stu-id="5e4e0-104">Databases contain OLAP and data mining objects, such as data sources, data source views, cubes, measures, measure groups, dimensions, attributes, hierarchies, mining structures, mining models and roles.</span></span>  
  
-   <span data-ttu-id="5e4e0-105">Assemblys enthalten benutzerdefinierte Funktionen, die die Funktionalität der mit den Sprachen Multidimensional Expressions (MDX) und Data Mining Extensions (DMX) bereitgestellten systeminternen Funktionen erweitern.</span><span class="sxs-lookup"><span data-stu-id="5e4e0-105">Assemblies contain user-defined functions that extend the functionality of the intrinsic functions provided with the Multidimensional Expressions (MDX) and Data Mining Extensions (DMX) languages.</span></span>  
  
 <span data-ttu-id="5e4e0-106">Das <xref:Microsoft.AnalysisServices.Database>-Objekt stellt den Container für alle Datenobjekte dar, die für ein Business Intelligence-Projekt benötigt werden (beispielsweise OLAP-Cubes, Dimensionen und Data Mining-Strukturen) sowie deren Unterstützungsobjekte (beispielsweise<xref:Microsoft.AnalysisServices.DataSource>, <xref:Microsoft.AnalysisServices.Account> und <xref:Microsoft.AnalysisServices.Role>).</span><span class="sxs-lookup"><span data-stu-id="5e4e0-106">The <xref:Microsoft.AnalysisServices.Database> object is the container for all data objects that are needed for a business intelligence project (such as OLAP cubes, dimensions, and data mining structures), and their supporting objects (such as <xref:Microsoft.AnalysisServices.DataSource>, <xref:Microsoft.AnalysisServices.Account>, and <xref:Microsoft.AnalysisServices.Role>).</span></span>  
  
 <span data-ttu-id="5e4e0-107">Ein <xref:Microsoft.AnalysisServices.Database>-Objekt bietet u.&#160;a. Zugriff auf folgende Objekte und Attribute:</span><span class="sxs-lookup"><span data-stu-id="5e4e0-107">A <xref:Microsoft.AnalysisServices.Database> object provides access to objects and attributes that include the following:</span></span>  
  
-   <span data-ttu-id="5e4e0-108">Eine Auflistung aller Cubes, auf die Sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="5e4e0-108">All cubes that you can access, as a collection.</span></span>  
  
-   <span data-ttu-id="5e4e0-109">Eine Auflistung aller Dimensionen, auf die Sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="5e4e0-109">All dimensions that you can access, as a collection.</span></span>  
  
-   <span data-ttu-id="5e4e0-110">Eine Auflistung aller Miningstrukturen, auf die Sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="5e4e0-110">All mining structures that you can access, as a collection.</span></span>  
  
-   <span data-ttu-id="5e4e0-111">Alle Datenquellen und Datenquellensichten in zwei Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="5e4e0-111">All data sources and data source views, as two collections.</span></span>  
  
-   <span data-ttu-id="5e4e0-112">Alle Rollen und Datenbankberechtigungen in zwei Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="5e4e0-112">All roles and database permissions, as two collections.</span></span>  
  
-   <span data-ttu-id="5e4e0-113">Der Sortierungswert der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="5e4e0-113">The collation value for the database.</span></span>  
  
-   <span data-ttu-id="5e4e0-114">Die geschätzte Größe der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="5e4e0-114">The estimated size of the database.</span></span>  
  
-   <span data-ttu-id="5e4e0-115">Der Sprachwert der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="5e4e0-115">The language value of the database.</span></span>  
  
-   <span data-ttu-id="5e4e0-116">Die sichtbare Einstellung der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="5e4e0-116">The visible setting for the database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5e4e0-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="5e4e0-117">In This Section</span></span>  
 <span data-ttu-id="5e4e0-118">In den folgenden Themen werden die Objekte beschrieben, die sowohl von OLAP- als auch von Data Mining-Funktionen in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5e4e0-118">The following topics describe objects shared by both OLAP and data mining features in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="5e4e0-119">Thema</span><span class="sxs-lookup"><span data-stu-id="5e4e0-119">Topic</span></span>|<span data-ttu-id="5e4e0-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e4e0-120">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5e4e0-121">Datenquellen in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="5e4e0-121">Data Sources in Multidimensional Models</span></span>](../data-sources-in-multidimensional-models.md)|<span data-ttu-id="5e4e0-122">Beschreibt eine Datenquelle in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e4e0-122">Describes a data source in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="5e4e0-123">Datenquellsichten in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="5e4e0-123">Data Source Views in Multidimensional Models</span></span>](../data-source-views-in-multidimensional-models.md)|<span data-ttu-id="5e4e0-124">Beschreibt ein logisches Datenmodell, das auf mindestens einer Datenquelle in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]basiert.</span><span class="sxs-lookup"><span data-stu-id="5e4e0-124">Describes a logical data model based on one or more data sources, in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="5e4e0-125">Cubes in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="5e4e0-125">Cubes in Multidimensional Models</span></span>](../cubes-in-multidimensional-models.md)|<span data-ttu-id="5e4e0-126">Beschreibt Cubes und Cubeobjekte, einschließlich Measures, Measuregruppen, Dimensionsverwendungbeziehungen, Berechnungen, Key Performance Indicators (KPIs), Aktionen, Übersetzungen, Partitionen und Perspektiven.</span><span class="sxs-lookup"><span data-stu-id="5e4e0-126">Describes cubes and cube objects, including measures, measure groups, dimension usage relationships, calculations, key performance indicators, actions, translations, partitions, and perspectives.</span></span>|  
|[<span data-ttu-id="5e4e0-127">Dimensionen &#40;Analysis Services – mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="5e4e0-127">Dimensions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../../multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md)|<span data-ttu-id="5e4e0-128">Beschreibt Dimensionen und Dimensionsobjekte, einschließlich Attribute, Attributbeziehungen, Hierarchien, Ebenen und Elemente.</span><span class="sxs-lookup"><span data-stu-id="5e4e0-128">Describes dimensions and dimension objects, including attributes, attribute relationships, hierarchies, levels, and members.</span></span>|  
|[<span data-ttu-id="5e4e0-129">Miningstrukturen &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="5e4e0-129">Mining Structures &#40;Analysis Services - Data Mining&#41;</span></span>](../../data-mining/mining-structures-analysis-services-data-mining.md)|<span data-ttu-id="5e4e0-130">Beschreibt Miningstrukturen und Miningobjekte, einschließlich Miningmodellen.</span><span class="sxs-lookup"><span data-stu-id="5e4e0-130">Describes mining structures and mining objects, including mining models.</span></span>|  
|[<span data-ttu-id="5e4e0-131">Sicherheitsrollen &#40;Analysis Services – Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="5e4e0-131">Security Roles  &#40;Analysis Services - Multidimensional Data&#41;</span></span>](security-roles-analysis-services-multidimensional-data.md)|<span data-ttu-id="5e4e0-132">Beschreibt eine Rolle, den Sicherheitsmechanismus, der zum Steuern des Zugriffs auf Objekte in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5e4e0-132">Describes a role, the security mechanism used to control access to objects in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="5e4e0-133">Verwaltung von mehrdimensionalen Modellassemblys</span><span class="sxs-lookup"><span data-stu-id="5e4e0-133">Multidimensional Model Assemblies Management</span></span>](../multidimensional-model-assemblies-management.md)|<span data-ttu-id="5e4e0-134">Beschreibt eine Assembly, eine Auflistung von benutzerdefinierten Funktionen, die zum Erweitern der Sprachen MDX und DMX in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5e4e0-134">Describes an assembly, a collection of user-defined functions used to extend the MDX and DMX languages, in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5e4e0-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5e4e0-135">See Also</span></span>  
 <span data-ttu-id="5e4e0-136">[Unterstützte Datenquellen &#40;mehrdimensionalen SSAS-&#41;](../supported-data-sources-ssas-multidimensional.md) </span><span class="sxs-lookup"><span data-stu-id="5e4e0-136">[Data Sources Supported &#40;SSAS Multidimensional&#41;](../supported-data-sources-ssas-multidimensional.md) </span></span>  
 <span data-ttu-id="5e4e0-137">[Mehrdimensionale Modelllösungen &#40;SSAS&#41;](../multidimensional-model-solutions-ssas.md) </span><span class="sxs-lookup"><span data-stu-id="5e4e0-137">[Multidimensional Model Solutions &#40;SSAS&#41;](../multidimensional-model-solutions-ssas.md) </span></span>  
 [<span data-ttu-id="5e4e0-138">Data Mining-Projektmappen</span><span class="sxs-lookup"><span data-stu-id="5e4e0-138">Data Mining Solutions</span></span>](../../data-mining/data-mining-solutions.md)  
  
  
