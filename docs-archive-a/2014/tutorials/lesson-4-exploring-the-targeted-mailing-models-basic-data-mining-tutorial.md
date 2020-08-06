---
title: 'Lektion 4: Untersuchen der Ziel-Mailing-Modelle (Lernprogramm zu Data Mining-Grundlagen) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 1e00c5b9-a9f8-4503-99ee-377c9cc02d7f
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 8659350b126164e06550acdbecec04bb07499c55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720470"
---
# <a name="lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial"></a><span data-ttu-id="8a366-102">Lektion 4: Untersuchen der Targeted Mailing-Modelle (Lernprogramm zu Data Mining-Grundlagen)</span><span class="sxs-lookup"><span data-stu-id="8a366-102">Lesson 4: Exploring the Targeted Mailing Models (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="8a366-103">Nachdem die Modelle im Projekt verarbeitet wurden, können Sie sie auf interessante Trends untersuchen.</span><span class="sxs-lookup"><span data-stu-id="8a366-103">After the models in your project have been processed, you can explore them to look for interesting trends.</span></span> <span data-ttu-id="8a366-104">Da Muster bei bloßer Betrachtung der Zahlen komplex und schwierig erscheinen können, bietet SQL Server Data Mining visuelle Tools, mit deren Hilfe die Daten untersucht und die Regeln und Beziehungen, die von den Algorithmen innerhalb der Daten ermittelt wurden, interpretiert werden können.</span><span class="sxs-lookup"><span data-stu-id="8a366-104">Because patterns can be complex and difficult simply by looking at numbers, SQL Server Data Mining provides some visual tools that help you investigate the data and understand the rules and relationships that the algorithms have discovered within the data.</span></span> <span data-ttu-id="8a366-105">Sie können auch verschiedene Genauigkeitstests verwenden, um das Dataset zu überprüfen bzw. um vor der Bereitstellung festzustellen, welches Modell am besten geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="8a366-105">You can also use a variety of accuracy tests to validate your dataset or discover which model performs best before you deploy it.</span></span>  
  
 <span data-ttu-id="8a366-106">Wenn Sie verwenden, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] um die Modelle zu untersuchen, wird jedes erstellte Modell auf der Registerkarte **Mining Modell-Viewer** im Data Mining-Designer aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="8a366-106">When you use [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to explore your models, each model you created is listed in the **Mining Model Viewer** tab in Data Mining Designer.</span></span> <span data-ttu-id="8a366-107">Sie können die Modelle mithilfe der Viewer untersuchen.</span><span class="sxs-lookup"><span data-stu-id="8a366-107">You can use the viewers to explore the models.</span></span> <span data-ttu-id="8a366-108">Diese Viewer sind auch in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8a366-108">These viewers are also available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="8a366-109">Jeder Algorithmus, den Sie zum Erstellen eines Modells in verwendet haben, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] gibt einen anderen Ergebnistyp zurück.</span><span class="sxs-lookup"><span data-stu-id="8a366-109">Each algorithm that you used to build a model in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] returns a different type of result.</span></span> <span data-ttu-id="8a366-110">Daher enthält [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] benutzerdefinierte Viewer für jede Art von Computerlernmodellen.</span><span class="sxs-lookup"><span data-stu-id="8a366-110">Therefore, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] provides custom viewers for each type of machine learning model.</span></span>  
  
 <span data-ttu-id="8a366-111">Wenn Sie Details anzeigen möchten, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] bietet auch einen HTML-Viewer mit dem Namen **Generic Content Tree Viewer**, der ausführliche Informationen über die Modelldaten und alle gefundenen Muster in einem semitabellarischen Format anzeigt.</span><span class="sxs-lookup"><span data-stu-id="8a366-111">If you want to get into details, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] also provides an HTML viewer, called the **Generic Content Tree Viewer**, that displays detailed information about the model data and any patterns that were found, in a semi-tabular format.</span></span> <span data-ttu-id="8a366-112">Weitere Informationen finden Sie unter [Durchsuchen eines Modells mit dem Microsoft Generic Content Tree Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="8a366-112">For more information, see [Browse a Model Using the Microsoft Generic Content Tree Viewer](../../2014/analysis-services/data-mining/browse-a-model-using-the-microsoft-generic-content-tree-viewer.md).</span></span>  
  
 <span data-ttu-id="8a366-113">In dieser Lektion werden die Ergebnisse von drei Modellen untersucht.</span><span class="sxs-lookup"><span data-stu-id="8a366-113">In this lesson you will look at the results from your three models.</span></span> <span data-ttu-id="8a366-114">Jeder Modelltyp basiert auf einem anderen Algorithmus und bietet unterschiedliche Einblicke in die Daten.</span><span class="sxs-lookup"><span data-stu-id="8a366-114">Each model type is based on a different algorithm and provides different insights into the data.</span></span>  
  
-   <span data-ttu-id="8a366-115">Das Decision Tree-Modell gibt Erklärungen zu Faktoren, die den Fahrradkauf beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="8a366-115">The Decision Tree model tells you about factors that influence bike buying.</span></span>  
  
-   <span data-ttu-id="8a366-116">Das Clustering-Modell gruppiert die Kunden nach Attributen, darunter das Fahrradkaufverhalten sowie andere ausgewählte Attribute.</span><span class="sxs-lookup"><span data-stu-id="8a366-116">The Clustering model groups your customers by attributes that include their bike buying behavior and other selected attributes.</span></span>  
  
-   <span data-ttu-id="8a366-117">Mit dem Naive Bayes-Modell können Sie die Beziehung zwischen verschiedenen Attributen untersuchen.</span><span class="sxs-lookup"><span data-stu-id="8a366-117">The Naive Bayes model enables you to explore the relationship between different attributes.</span></span>  
  
 <span data-ttu-id="8a366-118">Die folgenden Themen enthalten weitere Informationen zu den einzelnen Miningmodell-Viewern.</span><span class="sxs-lookup"><span data-stu-id="8a366-118">See the following topics to learn more about each of the mining model viewers.</span></span>  
  
-   [<span data-ttu-id="8a366-119">Untersuchen des Entscheidungsstruktur Modells &#40;grundlegenden Data Mining-Lernprogramm&#41;</span><span class="sxs-lookup"><span data-stu-id="8a366-119">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="8a366-120">Erkunden des Clustering-Modells &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="8a366-120">Exploring the Clustering Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-clustering-model-basic-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="8a366-121">Untersuchen des Naive Bayes-Modells &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="8a366-121">Exploring the Naive Bayes Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-naive-bayes-model-basic-data-mining-tutorial.md)  
  
 <span data-ttu-id="8a366-122">Alle drei Modelle können mit dem **Generic Content Tree Viewer**angezeigt werden, um Formeln, Datenwerte usw. zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="8a366-122">All three models can be viewed using the **Generic Content Tree Viewer**, to extract formulas, data values, and so forth.</span></span>  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="8a366-123">Erste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="8a366-123">First Task in Lesson</span></span>  
 [<span data-ttu-id="8a366-124">Untersuchen des Entscheidungsstruktur Modells &#40;grundlegenden Data Mining-Lernprogramm&#41;</span><span class="sxs-lookup"><span data-stu-id="8a366-124">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="8a366-125">Vorherige Lektion</span><span class="sxs-lookup"><span data-stu-id="8a366-125">Previous Lesson</span></span>  
 [<span data-ttu-id="8a366-126">Lektion 3: Hinzufügen und Verarbeiten von Modellen</span><span class="sxs-lookup"><span data-stu-id="8a366-126">Lesson 3: Adding and Processing Models</span></span>](../../2014/tutorials/lesson-3-adding-and-processing-models.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="8a366-127">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="8a366-127">Next Lesson</span></span>  
 [<span data-ttu-id="8a366-128">Lektion 5: Testen von Modellen &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="8a366-128">Lesson 5: Testing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-testing-models-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="8a366-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a366-129">See Also</span></span>  
 <span data-ttu-id="8a366-130">[Tasks und Anleitungen des Mining Modell-Viewers](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="8a366-130">[Mining Model Viewer Tasks and How-tos](../../2014/analysis-services/data-mining/mining-model-viewer-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="8a366-131">Data Mining-Modell-Viewer</span><span class="sxs-lookup"><span data-stu-id="8a366-131">Data Mining Model Viewers</span></span>](../../2014/analysis-services/data-mining/data-mining-model-viewers.md)  
  
  
