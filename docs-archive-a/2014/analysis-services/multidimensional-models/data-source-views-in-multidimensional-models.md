---
title: Datenquellen Sichten in mehrdimensionalen Modellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data source views [Analysis Services]
- data source views [Analysis Services], about data source views
- SQL Server Analysis Services, data source views
- data source views [Analysis Services], multiple
- Analysis Services, data source views
- multiple data source views
- SSAS, data source views
ms.assetid: 4c12376f-4fc2-492b-9a00-93eec34571ed
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1aef6b6d716ec71ac082ca8b7c042492c1712b1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725090"
---
# <a name="data-source-views-in-multidimensional-models"></a><span data-ttu-id="b3234-102">Datenquellensichten in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="b3234-102">Data Source Views in Multidimensional Models</span></span>
  <span data-ttu-id="b3234-103">Eine Datenquellensicht (DSV) ist eine Abstraktion einer relationalen Datenquelle, die die Basis für die in einem mehrdimensionalen Projekt erstellten Cubes und Dimensionen bildet.</span><span class="sxs-lookup"><span data-stu-id="b3234-103">A data source view (DSV) is an abstraction of a relational data source that becomes the basis of the cubes and dimensions you create in a multidimensional project.</span></span> <span data-ttu-id="b3234-104">Der Zweck eines DSVs besteht darin, Ihnen die Kontrolle über die im Projekt verwendeten Datenstrukturen zu verleihen und von den zugrundeliegenden Datenquellen (z. B., die Fähigkeit, Spalten umzubenennen, ohne die ursprüngliche Datenquelle direkt zu ändern oder zu verketten) unabhängig zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="b3234-104">The purpose of a DSV is to give you control over the data structures used in your project, and to work independently of the underlying data sources (for example, the ability to rename or concatenate columns without directly modifying the original data source).</span></span>  
  
 <span data-ttu-id="b3234-105">Sie können mehrere Datenquellensichten in einem Projekt oder einer Datenbank von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] auf der Grundlage einer oder mehrerer Datenquellen erstellen und die einzelnen Datenquellensichten so erstellen, dass sie die Anforderungen einer jeweils anderen Projektmappe erfüllen.</span><span class="sxs-lookup"><span data-stu-id="b3234-105">You can build multiple data source views in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database on one or more data sources, and construct each one to satisfy the requirements for a different solution.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="b3234-106">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="b3234-106">Related Tasks</span></span>  
 [<span data-ttu-id="b3234-107">Definieren einer Datenquellensicht &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b3234-107">Defining a Data Source View &#40;Analysis Services&#41;</span></span>](defining-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="b3234-108">Hinzufügen oder Entfernen von Tabellen oder Sichten in einer Datenquellensicht &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b3234-108">Adding or Removing Tables or Views in a Data Source View &#40;Analysis Services&#41;</span></span>](adding-or-removing-tables-or-views-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="b3234-109">Ändern von Eigenschaften in einer Datenquellensicht &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b3234-109">Change Properties in a Data Source View &#40;Analysis Services&#41;</span></span>](change-properties-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="b3234-110">Definieren von logischen Beziehungen in einer Datenquellensicht &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b3234-110">Define Logical Relationships in a Data Source View &#40;Analysis Services&#41;</span></span>](define-logical-relationships-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="b3234-111">Definieren logischer Primärschlüssel in einer Datenquellensicht &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b3234-111">Define Logical Primary Keys in a Data Source View &#40;Analysis Services&#41;</span></span>](define-logical-primary-keys-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="b3234-112">Definieren von benannten Berechnungen in einer Datenquellensicht &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b3234-112">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="b3234-113">Definieren von benannten Abfragen in einer Datenquellensicht &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b3234-113">Define Named Queries in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-queries-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="b3234-114">Ersetzen einer Tabelle oder einer benannten Abfrage in einer Datenquellensicht &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b3234-114">Replace a Table or a Named Query in a Data Source View &#40;Analysis Services&#41;</span></span>](replace-a-table-or-a-named-query-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="b3234-115">Verwenden von Diagrammen im Datenquellensicht-Designer &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b3234-115">Work with Diagrams in Data Source View Designer &#40;Analysis Services&#41;</span></span>](work-with-diagrams-in-data-source-view-designer-analysis-services.md)  
  
 [<span data-ttu-id="b3234-116">Durchsuchen von Daten in einer Datenquellensicht &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b3234-116">Explore Data in a Data Source View &#40;Analysis Services&#41;</span></span>](explore-data-in-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="b3234-117">Löschen einer Datenquellensicht &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b3234-117">Delete a Data Source View &#40;Analysis Services&#41;</span></span>](delete-a-data-source-view-analysis-services.md)  
  
 [<span data-ttu-id="b3234-118">Aktualisieren des Schemas in einer Datenquellensicht &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b3234-118">Refresh the Schema in a Data Source View &#40;Analysis Services&#41;</span></span>](refresh-the-schema-in-a-data-source-view-analysis-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="b3234-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b3234-119">See Also</span></span>  
 <span data-ttu-id="b3234-120">[Der Schemagenerierungs-Assistent &#40;Analysis Services&#41;](schema-generation-wizard-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="b3234-120">[Schema Generation Wizard &#40;Analysis Services&#41;](schema-generation-wizard-analysis-services.md) </span></span>  
 [<span data-ttu-id="b3234-121">Unterstützte Datenquellen &#40;mehrdimensionalen SSAS-&#41;</span><span class="sxs-lookup"><span data-stu-id="b3234-121">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](supported-data-sources-ssas-multidimensional.md)  
  
  
