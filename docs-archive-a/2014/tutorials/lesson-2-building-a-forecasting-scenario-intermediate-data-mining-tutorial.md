---
title: 'Lektion 2: Erstellung eines Vorhersage Szenarios (Data Mining-Lernprogramm für Fortgeschrittene) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- time series [Analysis Services]
- data mining [Analysis Services], tutorials
- tutorials [Data Mining]
ms.assetid: 9a988156-c900-4c22-97fa-f6b0c1aea9e2
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: c81d5846df0a37c2b4182cb92fea86ce6f3417a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608175"
---
# <a name="lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial"></a><span data-ttu-id="fadb6-102">Lektion 2: Erstellen eines Planungserstellungsszenarios (Data Mining-Lernprogramm für Fortgeschrittene)</span><span class="sxs-lookup"><span data-stu-id="fadb6-102">Lesson 2: Building a Forecasting Scenario (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="fadb6-103">Als Sales Analyst für [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)]wurden Sie aufgefordert, den Verkauf von Produkten für das nächste Jahr zu prognostizieren.</span><span class="sxs-lookup"><span data-stu-id="fadb6-103">As the sales analyst for [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], you have been asked to forecast the sales of products for the next year.</span></span> <span data-ttu-id="fadb6-104">Sie wurden insbesondere angehalten, Prognosen für unterschiedliche Regionen und Produktlinien zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="fadb6-104">In particular, you have been asked to compare forecasts for the different regions and product lines.</span></span> <span data-ttu-id="fadb6-105">Darüber hinaus sollen Sie feststellen, ob der Verkauf verschiedener Produkte je nach Jahreszeit Schwankungen unterliegt.</span><span class="sxs-lookup"><span data-stu-id="fadb6-105">Additionally, you have been asked to determine whether sales of different products vary depending on the time of the year.</span></span>  
  
 <span data-ttu-id="fadb6-106">In dieser Lektion fassen Sie die Vertriebsdaten des Unternehmens auf monatlicher Basis zusammen, um die angeforderten Informationen zu finden. Darüber hinaus unterteilen Sie die Verkaufszahlen in drei Regionen: Europa, Nordamerika und Pazifischer Raum.</span><span class="sxs-lookup"><span data-stu-id="fadb6-106">To find the requested information, in this lesson you will summarize the company's sales data at the monthly level, and you will also summarize sales figures by three regions: Europe, North America, and the Pacific.</span></span>  
  
 <span data-ttu-id="fadb6-107">Wenn Sie die Aufgaben in dieser Lektion ausgeführt haben, können Sie folgende Fragen beantworten:</span><span class="sxs-lookup"><span data-stu-id="fadb6-107">After you complete the tasks in this lesson, you will be able to answer the following questions:</span></span>  
  
-   <span data-ttu-id="fadb6-108">Welchen Schwankungen ist der Verkauf unterschiedlicher Fahrradmodelle im Laufe der Zeit unterworfen?</span><span class="sxs-lookup"><span data-stu-id="fadb6-108">How do the sales of different bike models change over time?</span></span>  
  
-   <span data-ttu-id="fadb6-109">Gibt es Unterschiede zwischen den Verkaufsmustern in den drei Regionen?</span><span class="sxs-lookup"><span data-stu-id="fadb6-109">Are there differences between the patterns for sales in the three regions?</span></span>  
  
-   <span data-ttu-id="fadb6-110">Können wir vorhersagen, zu welchem Zeitpunkt die meisten Verkäufe stattfinden?</span><span class="sxs-lookup"><span data-stu-id="fadb6-110">Can we forecast sales peaks?</span></span>  
  
 <span data-ttu-id="fadb6-111">Die Lektion kann in zwei Teilen durchgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="fadb6-111">The lesson can be completed in two parts:</span></span>  
  
-   <span data-ttu-id="fadb6-112">Der erste Teil bietet eine Einführung in die Grundlagen der Erstellung und Verwendung eines Zeitreihenmodells.</span><span class="sxs-lookup"><span data-stu-id="fadb6-112">Part One introduces the basics of how to create and use a time series model.</span></span>  
  
-   <span data-ttu-id="fadb6-113">Im zweiten Teil wird die Erstellung eines allgemeinen Zeitreihenmodells erläutert, das auf allen Regionen basiert.</span><span class="sxs-lookup"><span data-stu-id="fadb6-113">Part Two walks you through creation of a general time series model, based on all regions.</span></span> <span data-ttu-id="fadb6-114">Dieses allgemeine Modell kann für *Kreuzvorhersagen*verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fadb6-114">You can use this general model for *cross-prediction*.</span></span>  
  
 <span data-ttu-id="fadb6-115">Zum Durchführen der Aufgaben in dieser Lektion, die unten aufgelistet sind, verwenden Sie die [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] Datenquelle, die Sie in [Lektion 1: Erstellen der Data Mining ](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)-Data Mining-Projekt Mappe &#40;Data Mining-Lernprogramm für fortgeschrittene erstellt haben&#41;.</span><span class="sxs-lookup"><span data-stu-id="fadb6-115">To complete the tasks in this lesson, which are listed below, you will use the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source that you created in [Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="fadb6-116">Die Datumsangaben in der [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] -Beispieldatenbank wurden für diese Version aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="fadb6-116">The dates in the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] sample database have been updated for this release.</span></span> <span data-ttu-id="fadb6-117">Wenn Sie eine frühere Version von [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)]verwenden, können Sie das Modell anhand der folgenden Schritte erstellen, die angezeigten Ergebnisse weichen jedoch möglicherweise ab.</span><span class="sxs-lookup"><span data-stu-id="fadb6-117">If you use an earlier version of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)], you can build the model following these steps, but you might see different results.</span></span>  
  
 <span data-ttu-id="fadb6-118">**Erstellen eines einfachen Planungserstellungsmodells**</span><span class="sxs-lookup"><span data-stu-id="fadb6-118">**Creating a Simple Forecasting Model**</span></span>  
  
-   [<span data-ttu-id="fadb6-119">Hinzufügen einer Datenquellen Sicht für Vorhersage &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="fadb6-119">Adding a Data Source View for Forecasting &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="fadb6-120">Erstellen einer Planungsstruktur und eines Modells &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="fadb6-120">Creating a Forecasting Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-forecasting-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="fadb6-121">Ändern der Planungsstruktur &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="fadb6-121">Modifying the Forecasting Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/modifying-the-forecasting-structure-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="fadb6-122">Anpassen und Verarbeiten des Vorhersagemodells &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="fadb6-122">Customizing and Processing the Forecasting Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/customize-process-forecasting-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="fadb6-123">Untersuchen des Planungs Modells &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="fadb6-123">Exploring the Forecasting Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-forecasting-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="fadb6-124">Erstellen von Zeitreihen Vorhersagen &#40;Data Mining-Tutorial für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="fadb6-124">Creating Time Series Predictions &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="fadb6-125">**Erstellen eines allgemeinen Planungserstellungsmodells für Kreuzvorhersagen**</span><span class="sxs-lookup"><span data-stu-id="fadb6-125">**Creating a General Forecasting Model for Cross-Prediction**</span></span>  
  
-   [<span data-ttu-id="fadb6-126">Erweiterte Zeitreihen Vorhersagen &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="fadb6-126">Advanced Time Series Predictions &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/advanced-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="fadb6-127">Zeitreihen Vorhersagen mit aktualisierten Data &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="fadb6-127">Time Series Predictions using Updated Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-using-updated-data-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="fadb6-128">Zeitreihen Vorhersagen mit Ersetzungs Daten &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="fadb6-128">Time Series Predictions using Replacement Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-predictions-replacement-data-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="fadb6-129">Vergleichen von Vorhersagen für Prognosemodelle &#40;Data&#41;Mining-Lernprogramm für Fortgeschrittene</span><span class="sxs-lookup"><span data-stu-id="fadb6-129">Comparing Predictions for Forecasting Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/comparing-predictions-for-forecasting-models-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="fadb6-130">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="fadb6-130">Next Task in Lesson</span></span>  
 [<span data-ttu-id="fadb6-131">Hinzufügen einer Datenquellen Sicht für Vorhersage &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="fadb6-131">Adding a Data Source View for Forecasting &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-for-forecasting-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="fadb6-132">Grundlegendes zu den Anforderungen für ein Zeitreihen Modell &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="fadb6-132">Understanding the Requirements for a Time Series Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/time-series-model-requirements-intermediate-data-mining-tutorial.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="fadb6-133">Alle Lektionen</span><span class="sxs-lookup"><span data-stu-id="fadb6-133">All Lessons</span></span>  
 [<span data-ttu-id="fadb6-134">Lektion 1: Erstellen der Data Mining-Lösung für fortgeschrittene &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="fadb6-134">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="fadb6-135">Lektion 2: Planungserstellungsszenario (Data Mining-Tutorial für Fortgeschrittene)</span><span class="sxs-lookup"><span data-stu-id="fadb6-135">Lesson 2: Forecasting Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
 [<span data-ttu-id="fadb6-136">Lektion 3: Erstellen eines Warenkorbszenarios &#40;Data Mining-Tutorial für Fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="fadb6-136">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="fadb6-137">Lektion 4: Entwickeln eines Sequence Clustering-Szenarios &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="fadb6-137">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 [<span data-ttu-id="fadb6-138">Lektion 5: Erstellen von neuronalen Netzwerk- und logistischen Regressionsmodellen &#40;Data Mining-Tutorial für Fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="fadb6-138">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="fadb6-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fadb6-139">See Also</span></span>  
 <span data-ttu-id="fadb6-140">[Tutorial zu Data Mining-Grundlagen](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="fadb6-140">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 <span data-ttu-id="fadb6-141">[Data Mining-Lernprogramm für fortgeschrittene &#40;Analysis Services-Data Mining-&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="fadb6-141">[Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="fadb6-142">Microsoft Time Series-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="fadb6-142">Microsoft Time Series Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-time-series-algorithm.md)  
  
  
