---
title: Data Mining-Lösungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], about data mining
- data mining [Analysis Services], development
ms.assetid: 84f6548d-ebb0-4e10-9b29-66253fa0a04a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0ab4b5ddcc9958fa36d6c8ecae0e7fd79585b4fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616843"
---
# <a name="data-mining-solutions"></a><span data-ttu-id="c9c08-102">Data Mining-Projektmappen</span><span class="sxs-lookup"><span data-stu-id="c9c08-102">Data Mining Solutions</span></span>
  <span data-ttu-id="c9c08-103">Eine Data Mining-Projektmappe ist eine [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projektmappe, die ein oder mehrere Data Mining-Projekte enthält.</span><span class="sxs-lookup"><span data-stu-id="c9c08-103">A data mining solution is an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] solution that contains one or more data mining projects.</span></span>  
  
 <span data-ttu-id="c9c08-104">Die Themen in diesem Abschnitt enthalten Informationen zum Entwerfen und Implementieren einer integrierten Data Mining Lösung mithilfe von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9c08-104">The topics in this section provide information about how to design and implement an integrated data mining solution by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="c9c08-105">Eine Übersicht über den Data Mining-Entwurfsprozess und verwandte Tools finden Sie unter [Data Mining Concepts](data-mining-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="c9c08-105">For an overview of the data mining design process and related tools, see [Data Mining Concepts](data-mining-concepts.md).</span></span>  
  
 <span data-ttu-id="c9c08-106">Weitere Informationen zu zusätzlichen Projekttypen, die für Data Mining nützlich sind, finden Sie unter [Verwandte Projekte für Data Mining-Lösungen](data-mining-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="c9c08-106">For more information about additional projects types that are useful for data mining, see [Related Projects for Data Mining Solutions](data-mining-solutions.md).</span></span>  
  
 [<span data-ttu-id="c9c08-107">Vergleich der relationalen und mehrdimensionalen Projektmappen</span><span class="sxs-lookup"><span data-stu-id="c9c08-107">Relational vs. Multidimensional Solutions</span></span>](#bkmk_RelMD)  
  
 [<span data-ttu-id="c9c08-108">Bereitstellen von Data Mining-Projektmappen</span><span class="sxs-lookup"><span data-stu-id="c9c08-108">Deploying Data Mining Solutions</span></span>](#bkmk_Deploy)  
  
 [<span data-ttu-id="c9c08-109">Anleitungen für Projektmappen</span><span class="sxs-lookup"><span data-stu-id="c9c08-109">Solution Walkthroughs</span></span>](#bkmk_Walkthru)  
  
##  <a name="relational-vs-multidimensional-solutions"></a><a name="bkmk_RelMD"></a><span data-ttu-id="c9c08-110">Relationale und mehrdimensionale Lösungen</span><span class="sxs-lookup"><span data-stu-id="c9c08-110">Relational vs. Multidimensional Solutions</span></span>  
 <span data-ttu-id="c9c08-111">Eine Data Mining Lösung kann entweder auf mehrdimensionalen Daten basieren, d. h. auf einem vorhandenen Cube, oder auf rein relationalen Daten, wie z. b. Tabellen und Sichten in einer Data Warehouse, oder auf Textdateien, Excel-Arbeitsmappen oder anderen externen Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="c9c08-111">A data mining solution can be based either on multidimensional data-that is, an existing cube-or on purely relational data, such as the tables and views in a data warehouse, or on text files, Excel workbooks, or other external data sources.</span></span>  
  
-   <span data-ttu-id="c9c08-112">Sie können Data Mining-Objekte innerhalb einer vorhandenen mehrdimensionalen Datenbankprojektmappe erstellen.</span><span class="sxs-lookup"><span data-stu-id="c9c08-112">You can create data mining objects within an existing multidimensional database solution.</span></span>  
  
     <span data-ttu-id="c9c08-113">In der Regel würden Sie eine Projektmappe so erstellen, wenn Sie bereits einen Cube erstellt haben und Data Mining mit dem Cube als Datenquelle ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="c9c08-113">Typically you would create a solution like this if you have already created a cube and want to perform data mining by using the cube as a data source.</span></span> <span data-ttu-id="c9c08-114">Wenn Sie Modelle auf Grundlage eines Cubes verschieben und sichern, muss der Cube auch verschoben oder kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="c9c08-114">When you move and backup models based on a cube, the cube must also be moved or copied.</span></span>  
  
-   <span data-ttu-id="c9c08-115">Sie können eine Data Mining-Projektmappe erstellen, die nur Data Mining-Objekte enthält, einschließlich der unterstützenden Datenquellen und Datenquellensichten, und die nur die relationale Datenquelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="c9c08-115">You can create a data mining solution that contains only data mining objects, including the supporting data sources and data source views, and that uses relational data source only.</span></span>  
  
     <span data-ttu-id="c9c08-116">Dies ist die bevorzugte Methode zum Erstellen von Data Mining-Modellen, da die Verarbeitung und das Abfragen für relationale Datenquellen im Allgemeinen am schnellsten ist.</span><span class="sxs-lookup"><span data-stu-id="c9c08-116">This is the preferred method for creating data mining models, as processing and querying is generally fastest against relational data sources.</span></span> <span data-ttu-id="c9c08-117">Sie können sich auch Modelle zwischen Servern problemlos mit den Befehlen EXPORT und IMPORT verschieben und sichern.</span><span class="sxs-lookup"><span data-stu-id="c9c08-117">You can also easily move and backup models between servers by using the EXPORT and IMPORT commands.</span></span>  
  
##  <a name="deploying-data-mining-solutions"></a><a name="bkmk_Deploy"></a><span data-ttu-id="c9c08-118">Bereitstellen von Data Mining-Lösungen</span><span class="sxs-lookup"><span data-stu-id="c9c08-118">Deploying Data Mining Solutions</span></span>  
 <span data-ttu-id="c9c08-119">Die Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], für dir Sie die Projektmappe bereitstellen, muss in einem Modus ausgeführt werden, der mehrdimensionale Objekte und Data Mining-Objekte unterstützt. Sie können daher Data Mining-Objekte nicht in einer Instanz bereitstellen, die tabellarische Modelle oder PowerPivot-Daten hostet.</span><span class="sxs-lookup"><span data-stu-id="c9c08-119">The instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to which you deploy the solution must be running in a mode that supports multidimensional objects and data mining objects; that is, you cannot deploy data mining objects to an instance that hosts tabular models or PowerPivot data.</span></span>  
  
 <span data-ttu-id="c9c08-120">Wenn Sie in Visual Studio eine Data Mining-Projektmappe erstellen, müssen Sie demzufolge die Vorlage für multidimensionale Projekte bzw. Data Mining-Projekte von Analysis Services \*\*\*\* verwenden.</span><span class="sxs-lookup"><span data-stu-id="c9c08-120">Therefore, when you create a data mining solution in Visual Studio, be sure to use the template, **Analysis Services Multidimensional and Data Mining Project**.</span></span>  
  
 <span data-ttu-id="c9c08-121">Wenn Sie die Projektmappe bereitstellen, werden die für Data Mining verwendeten Objekte in der angegebenen [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz erstellt, und zwar in einer Datenbank mit dem gleichen Namen wie die Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="c9c08-121">When you deploy the solution, the objects used for data mining are created in the specified [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, in a database with the same name as the solution file.</span></span>  
  
 <span data-ttu-id="c9c08-122">Weitere Informationen zum Bereitstellen der relationalen und mehrdimensionalen Projektmappen finden Sie unter [Bereitstellen von Data Mining-Projektmappen](deployment-of-data-mining-solutions.md).</span><span class="sxs-lookup"><span data-stu-id="c9c08-122">For more information about how to deploy both relational and multidimensional solutions, see [Deployment of Data Mining Solutions](deployment-of-data-mining-solutions.md).</span></span>  
  
##  <a name="solution-walkthrough"></a><a name="bkmk_Walkthru"></a><span data-ttu-id="c9c08-123">Exemplarische Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="c9c08-123">Solution Walkthrough</span></span>  
 <span data-ttu-id="c9c08-124">Bietet eine Übersicht zum Erstellen von Data Mining-Projektmappen mit dem Data Mining-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="c9c08-124">Provides an overview of how to create data mining solutions by using the Data Mining Wizard.</span></span>  
  
 [<span data-ttu-id="c9c08-125">Erstellen einer relationalen Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="c9c08-125">Create a Relational Mining Structure</span></span>](create-a-relational-mining-structure.md)  
 <span data-ttu-id="c9c08-126">Erstellen Sie eine Miningstruktur aus relationalen Daten, Textdateien und anderen Quellen, die in einer Datenquellensicht kombiniert werden können.</span><span class="sxs-lookup"><span data-stu-id="c9c08-126">Create a mining structure from relational data, text files, and other sources that can be combined in a data source view.</span></span>  
  
 [<span data-ttu-id="c9c08-127">Erstellen einer OLAP-Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="c9c08-127">Create an OLAP Mining Structure</span></span>](create-an-olap-mining-structure.md)  
 <span data-ttu-id="c9c08-128">Erstellen Sie auf Grundlage von Daten in einem OLAP-Cube eine Miningstruktur.</span><span class="sxs-lookup"><span data-stu-id="c9c08-128">Create a mining structure based on data in an OLAP cube.</span></span> <span data-ttu-id="c9c08-129">Modelle, die Sie aus OLAP-Daten erstellen, können als Data Mining-Dimension gespeichert werden, oder Sie können den Satz mit Daten und die Modelle als neuen Cube speichern.</span><span class="sxs-lookup"><span data-stu-id="c9c08-129">Models that you create from OLAP data can be saved as a data mining dimension, or you can save the set of data and your models as a new cube.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9c08-130">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c9c08-130">In This Section</span></span>  
 [<span data-ttu-id="c9c08-131">Data Mining-Projekte</span><span class="sxs-lookup"><span data-stu-id="c9c08-131">Data Mining Projects</span></span>](data-mining-projects.md)  
  
 [<span data-ttu-id="c9c08-132">Verarbeiten von Data Mining-Objekten</span><span class="sxs-lookup"><span data-stu-id="c9c08-132">Processing Data Mining Objects</span></span>](processing-data-mining-objects.md)  
  
 [<span data-ttu-id="c9c08-133">Verwandte Projekte für Data Mining-Lösungen</span><span class="sxs-lookup"><span data-stu-id="c9c08-133">Related Projects for Data Mining Solutions</span></span>](data-mining-solutions.md)  
  
 [<span data-ttu-id="c9c08-134">Bereitstellen von Data Mining-Projektmappen</span><span class="sxs-lookup"><span data-stu-id="c9c08-134">Deployment of Data Mining Solutions</span></span>](deployment-of-data-mining-solutions.md)  
  
## <a name="related-tasks-and-topics"></a><span data-ttu-id="c9c08-135">Verwandte Aufgaben und Themen</span><span class="sxs-lookup"><span data-stu-id="c9c08-135">Related Tasks and Topics</span></span>  
 <span data-ttu-id="c9c08-136">Nachdem Sie eine grundlegende Data Mining-Projektmappe erstellt haben, einschließlich Datenquellen und einer Miningstruktur, können Sie auf der Projektmappe aufbauen, indem Sie neue Modelle hinzufügen, Modelle testen und vergleichen, Vorhersagen erstellen und mit Teilmengen der Daten experimentieren.</span><span class="sxs-lookup"><span data-stu-id="c9c08-136">After you have created a basic data mining solution, including data sources and a mining structure, you can build on the solution by adding new models, testing and comparing models, creating predictions, and experimenting with subsets of data.</span></span>  
  
 <span data-ttu-id="c9c08-137">Weitere Informationen finden Sie unter den folgenden Links:</span><span class="sxs-lookup"><span data-stu-id="c9c08-137">For more information, see the following links:</span></span>  
  
|<span data-ttu-id="c9c08-138">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="c9c08-138">Tasks</span></span>|<span data-ttu-id="c9c08-139">Themen</span><span class="sxs-lookup"><span data-stu-id="c9c08-139">Topics</span></span>|  
|-----------|------------|  
|<span data-ttu-id="c9c08-140">Testen Sie die Modelle, die Sie erstellen, überprüfen Sie die Qualität der Trainingsdaten, und erstellen Sie Diagramme, die die Genauigkeit von Data Mining-Modellen darstellen.</span><span class="sxs-lookup"><span data-stu-id="c9c08-140">Test the models you create, validate the quality of your training data, and create charts that represent the accuracy of data mining models.</span></span>|[<span data-ttu-id="c9c08-141">Tests und Überprüfung &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="c9c08-141">Testing and Validation &#40;Data Mining&#41;</span></span>](testing-and-validation-data-mining.md)|  
|<span data-ttu-id="c9c08-142">Trainieren Sie das Modell, indem Sie die Struktur und verwandte Modelle mit Daten auffüllen.</span><span class="sxs-lookup"><span data-stu-id="c9c08-142">Train the model by populating the structure and related models with data.</span></span> <span data-ttu-id="c9c08-143">Aktualisieren und erweitern Sie Modelle mit neuen Daten.</span><span class="sxs-lookup"><span data-stu-id="c9c08-143">Update and extend models with new data.</span></span>|[<span data-ttu-id="c9c08-144">Verarbeiten von Data Mining-Objekten</span><span class="sxs-lookup"><span data-stu-id="c9c08-144">Processing Data Mining Objects</span></span>](processing-data-mining-objects.md)|  
|<span data-ttu-id="c9c08-145">Passen Sie durch das Anwenden von Filtern auf die Trainingsdaten, Auswählen eines anderen Algorithmus oder Festlegen von erweiterten Algorithmusparametern ein Miningmodell an.</span><span class="sxs-lookup"><span data-stu-id="c9c08-145">Customize a mining model by applying filters to the training data, choosing a different algorithm, or setting advanced algorithm parameters.</span></span>|[<span data-ttu-id="c9c08-146">Anpassen von Miningmodellen und -strukturen</span><span class="sxs-lookup"><span data-stu-id="c9c08-146">Customize Mining Models and Structure</span></span>](customize-mining-models-and-structure.md)|  
|<span data-ttu-id="c9c08-147">Passen Sie ein Miningmodell durch Anwenden von Filtern auf die Daten an, die beim Trainieren des Modus verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c9c08-147">Customize a mining model by applying filters to the data used in training the mode.</span></span>|[<span data-ttu-id="c9c08-148">Hinzufügen von Miningmodellen zu einer Struktur &#40;Analysis Services - Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="c9c08-148">Add Mining Models to a Structure &#40;Analysis Services - Data Mining&#41;</span></span>](add-mining-models-to-a-structure-analysis-services-data-mining.md)|  
|<span data-ttu-id="c9c08-149">Aktualisieren und verwalten Sie Data Mining-Projektmappen.</span><span class="sxs-lookup"><span data-stu-id="c9c08-149">Update and manage data mining solutions.</span></span>|<span data-ttu-id="c9c08-150">Link TBD</span><span class="sxs-lookup"><span data-stu-id="c9c08-150">Link TBD</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c9c08-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9c08-151">See Also</span></span>  
 [<span data-ttu-id="c9c08-152">Data Mining-Tutorials &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="c9c08-152">Data Mining Tutorials &#40;Analysis Services&#41;</span></span>](../data-mining-tutorials-analysis-services.md)  
  
  
