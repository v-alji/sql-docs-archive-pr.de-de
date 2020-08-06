---
title: Bereitstellung von Data Mining-Lösungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models [Analysis Services], deploying
- deploying [Analysis Services], production environments
- deploying [Analysis Services - data mining]
- solutions [Analysis Services], deploying
- models [Analysis Services], data mining
ms.assetid: d83effc7-437d-42e9-8ac3-b65f79e27043
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5764be2f7530add2fa4cb028b288be69598bb95c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621264"
---
# <a name="deployment-of-data-mining-solutions"></a><span data-ttu-id="0df53-102">Bereitstellen von Data Mining-Projektmappen</span><span class="sxs-lookup"><span data-stu-id="0df53-102">Deployment of Data Mining Solutions</span></span>
  <span data-ttu-id="0df53-103">Der letzte Schritt im Data Mining-Prozess besteht darin, die Modelle in einer Produktionsumgebung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="0df53-103">The last step in the data mining process is to deploy the models to a production environment.</span></span> <span data-ttu-id="0df53-104">Die Bereitstellung ist wichtig, da dadurch die Modelle Benutzern zur Verfügung gestellt werden, damit Sie irgendeine der folgenden Aufgaben ausführen können:</span><span class="sxs-lookup"><span data-stu-id="0df53-104">Deployment is important because it makes the models available to users so that you can perform any of the following tasks:</span></span>  
  
-   <span data-ttu-id="0df53-105">Verwenden Sie die Modelle, um Vorhersagen und Geschäftsentscheidungen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="0df53-105">Use the models to create predictions and make business decisions.</span></span> <span data-ttu-id="0df53-106">Informationen zu den Tools, die Sie zum Erstellen von Abfragen verwenden können, finden Sie unter [Data Mining-Abfrageschnittstellen](data-mining-query-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0df53-106">For information about the tools you can use to create queries, see [Data Mining Query Interfaces](data-mining-query-tools.md).</span></span>  
  
-   <span data-ttu-id="0df53-107">Data Mining-Funktionen in eine Anwendung integrieren.</span><span class="sxs-lookup"><span data-stu-id="0df53-107">Embed data mining functionality directly into an application.</span></span> <span data-ttu-id="0df53-108">Sie können Analysis Management Objects (AMO) hinzufügen oder ein Assembly mit mehreren Objekten einbetten. Mit diesen Objekten kann Ihre Anwendung Miningstrukturen und -modelle erstellen, ändern, verarbeiten und löschen.</span><span class="sxs-lookup"><span data-stu-id="0df53-108">You can include Analysis Management Objects (AMO) or an assembly that contains a set of objects that your application can use to create, alter, process, and delete mining structures and mining models.</span></span>  
  
-   <span data-ttu-id="0df53-109">Erstellen Sie Berichte, mit denen Benutzer Vorhersagen anfordern, Trends anzeigen oder Modelle vergleichen können.</span><span class="sxs-lookup"><span data-stu-id="0df53-109">Create reports that let users request predictions, view trends, or compare models.</span></span>  
  
 <span data-ttu-id="0df53-110">Dieser Abschnitt enthält ausführliche Informationen über Bereitstellungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="0df53-110">This section provides detailed information about deployment options.</span></span>  
  
 [<span data-ttu-id="0df53-111">Anforderungen für die Bereitstellung von Data Mining-Lösungen</span><span class="sxs-lookup"><span data-stu-id="0df53-111">Requirements for Deployment of Data Mining Solutions</span></span>](#bkmk_Reqs)  
  
 [<span data-ttu-id="0df53-112">Bereitstellen von relationalen Projektmappen</span><span class="sxs-lookup"><span data-stu-id="0df53-112">Deploying a Relational Solution</span></span>](#bkmk_RelationalSltn)  
  
 [<span data-ttu-id="0df53-113">Bereitstellen von mehrdimensionalen Projektmappen</span><span class="sxs-lookup"><span data-stu-id="0df53-113">Deploying a Multidimensional Solution</span></span>](#bkmk_MDSltn)  
  
 [<span data-ttu-id="0df53-114">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="0df53-114">Related Resources</span></span>](#bkmk_Resources)  
  
## <a name="in-this-section"></a><span data-ttu-id="0df53-115">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0df53-115">In This Section</span></span>  
 [<span data-ttu-id="0df53-116">Bereitstellen von Data Mining-Lösungen für frühere Versionen von SQL Server</span><span class="sxs-lookup"><span data-stu-id="0df53-116">Deploy a Data Mining Solution to Previous Versions of SQL Server</span></span>](deploy-a-data-mining-solution-to-previous-versions-of-sql-server.md)  
  
 [<span data-ttu-id="0df53-117">Exportieren und Importieren von Data Mining-Objekten</span><span class="sxs-lookup"><span data-stu-id="0df53-117">Export and Import Data Mining Objects</span></span>](export-and-import-data-mining-objects.md)  
  
##  <a name="requirements-for-deployment-of-data-mining-solutions"></a><a name="bkmk_Reqs"></a> <span data-ttu-id="0df53-118">Anforderungen für die Bereitstellung von Data Mining-Projektmappen</span><span class="sxs-lookup"><span data-stu-id="0df53-118">Requirements for Deployment of Data Mining Solutions</span></span>  
 <span data-ttu-id="0df53-119">Die Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], für dir Sie die Projektmappe bereitstellen, muss in einem Modus ausgeführt werden, der mehrdimensionale Objekte und Data Mining-Objekte unterstützt. Sie können daher Data Mining-Objekte nicht in einer Instanz bereitstellen, die tabellarische Modelle oder PowerPivot-Daten hostet.</span><span class="sxs-lookup"><span data-stu-id="0df53-119">The instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to which you deploy the solution must be running in a mode that supports multidimensional objects and data mining objects; that is, you cannot deploy data mining objects to an instance that hosts tabular models or PowerPivot data.</span></span>  
  
 <span data-ttu-id="0df53-120">Wenn Sie in Visual Studio eine Data Mining-Projektmappe erstellen, müssen Sie demzufolge die Vorlage für multidimensionale Projekte bzw. Data Mining-Projekte von Analysis Services \*\*\*\* verwenden.</span><span class="sxs-lookup"><span data-stu-id="0df53-120">Therefore, when you create a data mining solution in Visual Studio, be sure to use the template, **Analysis Services Multidimensional and Data Mining Project**.</span></span>  
  
 <span data-ttu-id="0df53-121">Wenn Sie die Projektmappe bereitstellen, werden die für Data Mining verwendeten Objekte in der angegebenen [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz erstellt, und zwar in einer Datenbank mit dem gleichen Namen wie die Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="0df53-121">When you deploy the solution, the objects used for data mining are created in the specified [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, in a database with the same name as the solution file.</span></span>  
  
###  <a name="deploying-a-relational-solution"></a><a name="bkmk_RelationalSltn"></a><span data-ttu-id="0df53-122">Bereitstellen einer relationalen Lösung</span><span class="sxs-lookup"><span data-stu-id="0df53-122">Deploying a Relational Solution</span></span>  
 <span data-ttu-id="0df53-123">Wenn Sie eine relationale Data Mining-Projektmappe bereitstellen, werden die erforderlichen Data Mining-Objekte innerhalb einer neuen [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank erstellt, und die Objekte werden standardmäßig verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="0df53-123">When you deploy a relational data mining solution, the required data mining objects are created within a new [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, and the objects are processed by default.</span></span> <span data-ttu-id="0df53-124">Sie können die Verarbeitungsoptionen mithilfe der Konfigurationseigenschaft für die Verarbeitungsoption \*\*\*\* ändern.</span><span class="sxs-lookup"><span data-stu-id="0df53-124">You can change processing options by using the configuration property, **Processing Option**.</span></span> <span data-ttu-id="0df53-125">Weitere Informationen finden Sie unter [Konfigurieren von Analysis Services-Projekteigenschaften &#40;SSDT&#41;](../multidimensional-models/configure-analysis-services-project-properties-ssdt.md)erstellt.</span><span class="sxs-lookup"><span data-stu-id="0df53-125">For more information, see [Configure Analysis Services Project Properties &#40;SSDT&#41;](../multidimensional-models/configure-analysis-services-project-properties-ssdt.md).</span></span>  
  
 <span data-ttu-id="0df53-126">Standardmäßig werden nur inkrementelle Änderungen jedes Mal bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="0df53-126">By default, only incremental changes are deployed each time.</span></span> <span data-ttu-id="0df53-127">Sie können demnach ein Miningmodell ändern, und wenn Sie das Projekt erneut bereitstellen, wird nur das Miningmodell aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0df53-127">In other words, you can modify a mining model, and when you re-deploy the project, only that mining model would be updated.</span></span> <span data-ttu-id="0df53-128">Wenn jedoch mehrere Clients die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank bearbeiten, kann dies zu Fehlern führen.</span><span class="sxs-lookup"><span data-stu-id="0df53-128">However, if you have multiple clients editing the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, this can lead to errors.</span></span> <span data-ttu-id="0df53-129">Ändern Sie die Eigenschaft **Bereitstellungsmodus** , um den Standardbereitstellungsmodus zu ändern, damit die gesamte Datenbank aktualisiert wird, wenn Sie die Projektmappe bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0df53-129">To change the default deployment mode so that the entire database is refreshed when you deploy the solution, change the **Deployment Mode** property</span></span>  
  
 <span data-ttu-id="0df53-130">In einer relationalen Data Mining-Projektmappe sind die einzigen bereitzustellenden Objekte die Datenquellendefinition, sämtliche verwendeten Datenquellensichten, die Miningstrukturen und alle abhängigen Miningmodelle.</span><span class="sxs-lookup"><span data-stu-id="0df53-130">In a relational data mining solution, the only objects that must be deployed are the data source definition, any data source views that were used, the mining structures, and all dependent mining models.</span></span>  
  
###  <a name="deploying-a-multidimensional-solution"></a><a name="bkmk_MDSltn"></a><span data-ttu-id="0df53-131">Bereitstellen einer mehrdimensionalen Lösung</span><span class="sxs-lookup"><span data-stu-id="0df53-131">Deploying a Multidimensional Solution</span></span>  
 <span data-ttu-id="0df53-132">Wenn Sie eine mehrdimensionale Data Mining-Projektmappe bereitstellen, erstellt diese Projektmappe die Data Mining-Objekte in der gleichen Datenbank wie die des Quellcubes.</span><span class="sxs-lookup"><span data-stu-id="0df53-132">When you deploy a multidimensional data mining solution, this solution creates your data mining objects within the same database as the source cube.</span></span>  
  
 <span data-ttu-id="0df53-133">Wenn Sie die Miningstruktur oder das Miningmodell verarbeiten, müssen Sie auch den Quellcube verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0df53-133">When you process the mining structure or mining model, you must process the source cube as well.</span></span> <span data-ttu-id="0df53-134">Daher kann es länger dauern, eine Projektmappe bereitzustellen, die OLAP-Miningmodelle verwendet, als eine relationale Data Mining-Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="0df53-134">For this reason, deploying a solution that uses OLAP mining models can take longer than relational data mining solutions.</span></span>  
  
 <span data-ttu-id="0df53-135">In der Regel verwenden Data Mining-Objekte auch die gleichen Datenquellen und die Datenquellensichten, die für den Cube verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0df53-135">Typically data mining objects also use the same data sources and data source views that are used for the cube.</span></span> <span data-ttu-id="0df53-136">Sie können jedoch auch Datenquellen und Datenquellenansichten hinzufügen, die speziell auf Data Mining abzielen.</span><span class="sxs-lookup"><span data-stu-id="0df53-136">However, you can add data sources and data source views that are targeted specifically to data mining.</span></span> <span data-ttu-id="0df53-137">Ein Cube würde beispielsweise in der Regel keine Daten über potenzielle Kunden oder externe Daten enthalten, die in mehrdimensionalen Objekten nicht verwendete Daten.</span><span class="sxs-lookup"><span data-stu-id="0df53-137">For example, typically a cube would not contain data about prospective clients, or external data not used in the multidimensional objects.</span></span>  
  
##  <a name="related-resources"></a><a name="bkmk_Resources"></a><span data-ttu-id="0df53-138">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="0df53-138">Related Resources</span></span>  
 [<span data-ttu-id="0df53-139">Verschieben von Data Mining-Objekten</span><span class="sxs-lookup"><span data-stu-id="0df53-139">Moving Data Mining Objects</span></span>](moving-data-mining-objects.md)  
  
 <span data-ttu-id="0df53-140">Wenn das Modell nur auf relationalen Daten basiert, ist das Exportieren und Importieren von Objekten mit DMX die einfachste Möglichkeit, Modelle zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="0df53-140">If your model is based on relational data only, exporting and importing objects using DMX is the easiest way to move models.</span></span>  
  
 [<span data-ttu-id="0df53-141">Verschieben einer Analysis Services Datenbank</span><span class="sxs-lookup"><span data-stu-id="0df53-141">Move an Analysis Services Database</span></span>](../multidimensional-models/move-an-analysis-services-database.md)  
  
 <span data-ttu-id="0df53-142">Wenn Modelle einen Cube als Datenquelle verwenden, sind weitere Informationen über das Verschieben von Modellen und deren Cubedatenunterstützung diesem Thema zu entnehmen.</span><span class="sxs-lookup"><span data-stu-id="0df53-142">When models use a cube as a data source, refer to this topic for more information about how to move models and their supporting cube data.</span></span>  
  
 [<span data-ttu-id="0df53-143">Bereitstellen von Analysis Services-Projekten &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="0df53-143">Deploy Analysis Services Projects &#40;SSDT&#41;</span></span>](../multidimensional-models/deploy-analysis-services-projects-ssdt.md)  
  
 <span data-ttu-id="0df53-144">Bietet allgemeine Informationen über die Bereitstellungen von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekten und beschreibt die Eigenschaften, die als Teil der Projektkonfiguration festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="0df53-144">Provides general information about deployment of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projects, and describes the properties that you can set as part of the project configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0df53-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0df53-145">See Also</span></span>  
 <span data-ttu-id="0df53-146">[Objekt Verarbeitung für mehrdimensionale Modelle](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="0df53-146">[Multidimensional Model Object Processing](../multidimensional-models/processing-a-multidimensional-model-analysis-services.md) </span></span>  
 <span data-ttu-id="0df53-147">[Schnittstellen für Data Mining-Abfragen](data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="0df53-147">[Data Mining Query Interfaces](data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="0df53-148">Anforderungen und Überlegungen zur Verarbeitung &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="0df53-148">Processing Requirements and Considerations &#40;Data Mining&#41;</span></span>](processing-requirements-and-considerations-data-mining.md)  
  
  
