---
title: 'Lektion 1: Definieren einer Datenquellen Sicht in einem Analysis Services Projekt | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 7d3ffabd-78ae-4204-8323-29949d030c16
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8a3d69225217154e5072d0cd34349a247730ddaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724286"
---
# <a name="lesson-1-defining-a-data-source-view-within-an-analysis-services-project"></a><span data-ttu-id="84bb6-102">Lektion 1: Definieren einer Datenquellensicht innerhalb eines Analysis Services-Projekts</span><span class="sxs-lookup"><span data-stu-id="84bb6-102">Lesson 1: Defining a Data Source View within an Analysis Services Project</span></span>
  <span data-ttu-id="84bb6-103">Der Entwurf einer Business Intelligence-Anwendung in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] beginnt mit dem Erstellen eines [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Projekts in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="84bb6-103">Designing a business intelligence application in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] starts with creating an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="84bb6-104">Innerhalb dieses Projekts definieren Sie alle Elemente in Ihrer Projektmappe beginnend mit einer Datenquellensicht.</span><span class="sxs-lookup"><span data-stu-id="84bb6-104">Within this project, you define all the elements of your solution, starting with a data source view.</span></span>  
  
 <span data-ttu-id="84bb6-105">Diese Lektion enthält die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="84bb6-105">This lesson contains the following tasks:</span></span>  
  
 [<span data-ttu-id="84bb6-106">Erstellen eines Analysis Services-Projekts</span><span class="sxs-lookup"><span data-stu-id="84bb6-106">Creating an Analysis Services Project</span></span>](lesson-1-1-creating-an-analysis-services-project.md)  
 <span data-ttu-id="84bb6-107">In dieser Aufgabe erstellen Sie das [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Projekt basierend auf einer mehrdimensionalen [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Modellvorlage.</span><span class="sxs-lookup"><span data-stu-id="84bb6-107">In this task, you create the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project, based on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] multidimensional model template.</span></span>  
  
 [<span data-ttu-id="84bb6-108">Definieren einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="84bb6-108">Defining a Data Source</span></span>](lesson-1-2-defining-a-data-source.md)  
 <span data-ttu-id="84bb6-109">In dieser Aufgabe geben Sie die **AdventureWorksDW2012** -Datenbank als Datenquelle für die Dimensionen und Cubes von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] an, die Sie in den folgenden Lektionen definieren.</span><span class="sxs-lookup"><span data-stu-id="84bb6-109">In this task, you specify the **AdventureWorksDW2012** database as the data source for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dimensions and cubes that you will define in subsequent lessons.</span></span>  
  
 [<span data-ttu-id="84bb6-110">Definieren einer Datenquellensicht</span><span class="sxs-lookup"><span data-stu-id="84bb6-110">Defining a Data Source View</span></span>](lesson-1-3-defining-a-data-source-view.md)  
 <span data-ttu-id="84bb6-111">In dieser Aufgabe definieren Sie eine einzelne einheitliche Sicht der Metadaten aus ausgewählten Tabellen in der **AdventureWorksDW2012** -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="84bb6-111">In this task, you define a single unified view of the metadata from selected tables in the **AdventureWorksDW2012** database.</span></span>  
  
 [<span data-ttu-id="84bb6-112">Ändern von Standardtabellennamen</span><span class="sxs-lookup"><span data-stu-id="84bb6-112">Modifying Default Table Names</span></span>](lesson-1-4-modifying-default-table-names.md)  
 <span data-ttu-id="84bb6-113">In dieser Aufgabe ändern Sie Tabellennamen in der Datenquellensicht, sodass die Namen von nachfolgenden [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Objekten, die Sie definieren, benutzerfreundlicher werden.</span><span class="sxs-lookup"><span data-stu-id="84bb6-113">In this task, you modify table names in the data source view, so that the names of subsequent [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] objects that you define will be more user-friendly.</span></span>  
  
 <span data-ttu-id="84bb6-114">Vergleichen Sie die Ergebnisse mit einer Beispielprojektdatei, die für diese Lektion erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="84bb6-114">Compare your results against a sample project file that was built for this lesson.</span></span> <span data-ttu-id="84bb6-115">Weitere Informationen zum Herunterladen der Beispielprojekte für dieses Lernprogramm finden Sie auf der Codeplex-Website auf der Seite mit Produktbeispielen unter [SSAS Multidimensional Model Projects for SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=221866) .</span><span class="sxs-lookup"><span data-stu-id="84bb6-115">For more information about downloading the sample projects that go with this tutorial, see [SSAS Multidimensional Model Projects for SQL Server 2012](https://go.microsoft.com/fwlink/p/?LinkID=221866) on the product samples page on codeplex.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="84bb6-116">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="84bb6-116">Next Lesson</span></span>  
 [<span data-ttu-id="84bb6-117">Lektion 2: Definieren und Bereitstellen eines Cubes</span><span class="sxs-lookup"><span data-stu-id="84bb6-117">Lesson 2: Defining and Deploying a Cube</span></span>](lesson-2-defining-and-deploying-a-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="84bb6-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="84bb6-118">See Also</span></span>  
 <span data-ttu-id="84bb6-119">[Erstellen eines Analysis Services Projekts &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md) </span><span class="sxs-lookup"><span data-stu-id="84bb6-119">[Create an Analysis Services Project &#40;SSDT&#41;](multidimensional-models/create-an-analysis-services-project-ssdt.md) </span></span>  
 <span data-ttu-id="84bb6-120">[Unterstützte Datenquellen &#40;mehrdimensionalen SSAS-&#41;](multidimensional-models/supported-data-sources-ssas-multidimensional.md) </span><span class="sxs-lookup"><span data-stu-id="84bb6-120">[Data Sources Supported &#40;SSAS Multidimensional&#41;](multidimensional-models/supported-data-sources-ssas-multidimensional.md) </span></span>  
 <span data-ttu-id="84bb6-121">[Datenquellen Sichten in mehrdimensionalen Modellen](multidimensional-models/data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="84bb6-121">[Data Source Views in Multidimensional Models](multidimensional-models/data-source-views-in-multidimensional-models.md) </span></span>  
 <span data-ttu-id="84bb6-122">[Analysis Services Tutorial-Szenario](analysis-services-tutorial-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="84bb6-122">[Analysis Services Tutorial Scenario](analysis-services-tutorial-scenario.md) </span></span>  
 [<span data-ttu-id="84bb6-123">Mehrdimensionale Modellierung &#40;Adventure Works-Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="84bb6-123">Multidimensional Modeling &#40;Adventure Works Tutorial&#41;</span></span>](multidimensional-modeling-adventure-works-tutorial.md)  
  
  
