---
title: 'Lektion 4: Entwickeln eines Sequenz Cluster Szenarios (Data Mining-Lernprogramm für Fortgeschrittene) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], tutorials
- sequence clustering algorithms [Analysis Services]
- tutorials [Data Mining]
ms.assetid: 63436bbd-0f73-4012-b6f1-358c81e4d92a
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 0f417c685d8af898de7c66ffe82045fa76b582e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694858"
---
# <a name="lesson-4-building-a-sequence-clustering-scenario-intermediate-data-mining-tutorial"></a><span data-ttu-id="b06f0-102">Lektion 4: Erstellen eines Sequenzclusterszenarios (Data Mining-Lernprogramm für Fortgeschrittene)</span><span class="sxs-lookup"><span data-stu-id="b06f0-102">Lesson 4: Building a Sequence Clustering Scenario (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="b06f0-103">Die Marketingabteilung von [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] möchte verstehen, wie sich Kunden auf der [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] -Website bewegen.</span><span class="sxs-lookup"><span data-stu-id="b06f0-103">The marketing department of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] wants to understand how customers move through the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] Web site.</span></span> <span data-ttu-id="b06f0-104">Das Unternehmen vermutet, dass es ein Muster für die Reihenfolge gibt, in der Kunden Produkte in ihre Einkaufskörbe legen.</span><span class="sxs-lookup"><span data-stu-id="b06f0-104">The company suspects that there is a pattern to the order in which customers put products into their shopping baskets.</span></span> <span data-ttu-id="b06f0-105">Die Reihenfolge der Einkaufssequenzen soll analysiert werden, um zu ermitteln, wie Kunden ihren Einkaufskörben zugehörige Elemente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b06f0-105">They want to analyze the order of purchase sequences to learn how customers add related items to their baskets.</span></span> <span data-ttu-id="b06f0-106">Anhand dieser Informationen kann die Website dann so angepasst werden, dass Kunden angeregt werden, weitere Produkte zu kaufen.</span><span class="sxs-lookup"><span data-stu-id="b06f0-106">They can then use this information to streamline the flow of the Web site so that it leads customers to purchase additional products.</span></span>  
  
 <span data-ttu-id="b06f0-107">Wenn Sie die Aufgaben in dieser Lektion ausgeführt haben, haben Sie ein Miningmodell erstellt, mit dem Sie, durch die Anwendung des [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering-Algorithmus, das nächste Element vorhersagen können, das Kunden in ihren Einkaufskorb legen.</span><span class="sxs-lookup"><span data-stu-id="b06f0-107">After you complete the tasks in this lesson, you will have created a mining model that uses the [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering algorithm to predict the next item that customers will put into their shopping baskets.</span></span> <span data-ttu-id="b06f0-108">Sie werden zwei Versionen des Modells ausprobieren: Eine analysiert nur die Reihenfolge der Produkte, während die andere einige zusätzliche demografische Kundendaten zum Clustering enthält.</span><span class="sxs-lookup"><span data-stu-id="b06f0-108">You will experiment with two versions of the model: one that analyzes only the order of products in the basket, and one that contains some additional customer demographics for clustering.</span></span> <span data-ttu-id="b06f0-109">Abschließend werden Sie anhand der Modelle Vorhersagen erstellen, mit denen Sie Kunden bestimmte Produkte empfehlen können.</span><span class="sxs-lookup"><span data-stu-id="b06f0-109">Finally, you will use the models to create predictions that you can use to recommend products to customers.</span></span>  
  
 <span data-ttu-id="b06f0-110">Um die Aufgaben in der Lektion abzuschließen, verwenden Sie die Market Basket-Mining Struktur, die Sie in [Lektion 3: Erstellen eines Market Basket-Szenarios &#40;Data Mining ](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)-Lernprogramm für fortgeschrittene erstellt haben&#41;.</span><span class="sxs-lookup"><span data-stu-id="b06f0-110">To complete the tasks in the lesson, you will use the market basket mining structure that you created in [Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md).</span></span> <span data-ttu-id="b06f0-111">Diese Lektion enthält die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="b06f0-111">This lesson contains the following tasks:</span></span>  
  
-   [<span data-ttu-id="b06f0-112">Erstellen einer Sequence Clustering-Mining Modellstruktur &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="b06f0-112">Creating a Sequence Clustering Mining Model Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-sequence-clustering-mining-model-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="b06f0-113">Verarbeiten des Sequenzclustermodells</span><span class="sxs-lookup"><span data-stu-id="b06f0-113">Processing the Sequence Clustering Model</span></span>](../../2014/tutorials/processing-the-sequence-clustering-model.md)  
  
-   [<span data-ttu-id="b06f0-114">Erkunden des Sequence Clustering-Modells &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="b06f0-114">Exploring the Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-sequence-clustering-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="b06f0-115">Erstellen eines zugehörigen Sequence Clustering-Modells &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="b06f0-115">Creating a Related Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-related-sequence-clustering-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="b06f0-116">Erstellen von Vorhersagen für ein Sequenz Cluster Modell &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="b06f0-116">Creating Predictions on a Sequence Clustering Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-on-model-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b06f0-117">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="b06f0-117">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b06f0-118">Erstellen einer Sequence Clustering-Mining Modellstruktur &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="b06f0-118">Creating a Sequence Clustering Mining Model Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-sequence-clustering-mining-model-intermediate-data-mining.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="b06f0-119">Alle Lektionen</span><span class="sxs-lookup"><span data-stu-id="b06f0-119">All Lessons</span></span>  
 [<span data-ttu-id="b06f0-120">Lektion 1: Erstellen der Data Mining-Lösung für fortgeschrittene &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="b06f0-120">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="b06f0-121">Lektion 2: Erstellung eines Vorhersage Szenarios &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="b06f0-121">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="b06f0-122">Lektion 3: Erstellen eines Warenkorbszenarios &#40;Data Mining-Tutorial für Fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="b06f0-122">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="b06f0-123">Lektion 4: Sequenzclusterszenarios (Data Mining-Tutorial für Fortgeschrittene).</span><span class="sxs-lookup"><span data-stu-id="b06f0-123">Lesson 4: Sequence Clustering Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
 [<span data-ttu-id="b06f0-124">Lektion 5: Erstellen von neuronalen Netzwerk- und logistischen Regressionsmodellen &#40;Data Mining-Tutorial für Fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="b06f0-124">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="b06f0-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b06f0-125">See Also</span></span>  
 <span data-ttu-id="b06f0-126">[Tutorial zu Data Mining-Grundlagen](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="b06f0-126">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="b06f0-127">Data Mining-Lernprogramm für fortgeschrittene &#40;Analysis Services-Data Mining-&#41;</span><span class="sxs-lookup"><span data-stu-id="b06f0-127">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
  
