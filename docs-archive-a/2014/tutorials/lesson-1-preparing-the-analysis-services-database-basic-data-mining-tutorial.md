---
title: 'Lektion 1: Vorbereiten der Analysis Services Datenbank (Lernprogramm zu Data Mining-Grundlagen) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2a796977-6568-4705-9d27-86a9b36658c2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 07647a940851fbdbdc65357e168747662dc88380
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726397"
---
# <a name="lesson-1-preparing-the-analysis-services-database-basic-data-mining-tutorial"></a><span data-ttu-id="b284a-102">Lektion 1: Vorbereiten der Analysis Services-Datenbank (Lernprogramm zu Data Mining-Grundlagen)</span><span class="sxs-lookup"><span data-stu-id="b284a-102">Lesson 1: Preparing the Analysis Services Database (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="b284a-103">Sie sind ein neuer Mitarbeiter von [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] und wurden mit der Entwicklung einer Business Intelligence-Anwendung in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]beauftragt.</span><span class="sxs-lookup"><span data-stu-id="b284a-103">You are a new employee of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] who has been tasked with designing a business intelligence application in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span> [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)]<span data-ttu-id="b284a-104">hoffen, dass Sie Ihre [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Data Mining Erlebnisses nutzen können, um interessante und aussagekräftige Informationen über Personen zu ermitteln, die Fahrräder gekauft haben.</span><span class="sxs-lookup"><span data-stu-id="b284a-104">hopes to leverage your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data mining experience to discover interesting and actionable information about people who have purchased bicycles.</span></span> <span data-ttu-id="b284a-105">Das Unternehmen möchte, dass Sie vorhersagen, welche potenziellen Kunden höchstwahrscheinlich in der Zukunft ein Fahrrad kaufen werden.</span><span class="sxs-lookup"><span data-stu-id="b284a-105">They then want you to predict which prospective customers are most likely to purchase a bicycle in the future.</span></span>  
  
 <span data-ttu-id="b284a-106">Das Entwerfen dieser Anwendung in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] beginnt mit der Erstellung in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] eines Projekts, das [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] auf der [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Projektvorlage für mehrdimensionale Modellierung und Data Mining basiert.</span><span class="sxs-lookup"><span data-stu-id="b284a-106">Designing this application in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] starts with the creation in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] of a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project based on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project template for multidimensional modeling and data mining.</span></span> <span data-ttu-id="b284a-107">Wenn Sie ein [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Projekt angelegt haben, definieren Sie eine oder mehrere Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="b284a-107">After you create an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, you define one or more data sources.</span></span> <span data-ttu-id="b284a-108">Dann definieren Sie aus ausgewählten Tabellen und Sichten aus den Datenquellen eine Sicht der Metadaten, die als *Datenquellensicht*bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="b284a-108">Then, you define a view of the metadata, called a *data source view*, from selected tables and views from the data sources.</span></span>  
  
 <span data-ttu-id="b284a-109">In dieser Lektion legen Sie ein [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Projekt an, definieren eine einzelne Datenquelle und fügen einer Datenquellensicht eine Teilmenge von Tabellen hinzu.</span><span class="sxs-lookup"><span data-stu-id="b284a-109">In this lesson, you will create an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, define a single data source, and add a subset of tables to a data source view.</span></span> <span data-ttu-id="b284a-110">Diese Lektion enthält die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="b284a-110">This lesson includes the following tasks:</span></span>  
  
 [<span data-ttu-id="b284a-111">Erstellen eines Analysis Services Projekts &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="b284a-111">Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="b284a-112">Erstellen einer Datenquelle &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="b284a-112">Creating a Data Source &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="b284a-113">Erstellen einer Datenquellen Sicht &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="b284a-113">Creating a Data Source View &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-view-basic-data-mining-tutorial.md)  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="b284a-114">Erste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="b284a-114">First Task in Lesson</span></span>  
 [<span data-ttu-id="b284a-115">Erstellen eines Analysis Services Projekts &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="b284a-115">Creating an Analysis Services Project &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-an-analysis-services-project-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="b284a-116">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="b284a-116">Next Lesson</span></span>  
 [<span data-ttu-id="b284a-117">Lektion 2: aufbauen einer Ziel-Mailing Struktur &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="b284a-117">Lesson 2: Building a Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="b284a-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b284a-118">See Also</span></span>  
 <span data-ttu-id="b284a-119">[Datenquellen Sichten in mehrdimensionalen Modellen](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models) </span><span class="sxs-lookup"><span data-stu-id="b284a-119">[Data Source Views in Multidimensional Models](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models) </span></span>  
 <span data-ttu-id="b284a-120">[Unterstützte Datenquellen &#40;mehrdimensionalen SSAS-&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/supported-data-sources-ssas-multidimensional) </span><span class="sxs-lookup"><span data-stu-id="b284a-120">[Data Sources Supported &#40;SSAS Multidimensional&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/supported-data-sources-ssas-multidimensional) </span></span>  
 <span data-ttu-id="b284a-121">[Erstellen von Analysis Services Projekten &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span><span class="sxs-lookup"><span data-stu-id="b284a-121">[Build Analysis Services Projects &#40;SSDT&#41;](https://docs.microsoft.com/analysis-services/multidimensional-models/build-analysis-services-projects-ssdt) </span></span>  
 [<span data-ttu-id="b284a-122">Erstellen eines Analysis Services-Projekts</span><span class="sxs-lookup"><span data-stu-id="b284a-122">Creating an Analysis Services Project</span></span>](../analysis-services/lesson-1-1-creating-an-analysis-services-project.md)  
  
  
