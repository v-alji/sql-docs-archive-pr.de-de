---
title: 'Lektion 3: aufbauen eines Market Basket-Szenarios (Data Mining-Lernprogramm für Fortgeschrittene) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining [Analysis Services], tutorials
- association algorithms [Analysis Services]
- nested tables
- tutorials [Data Mining]
ms.assetid: 651eef38-772e-4d97-af51-075b1b27fc5a
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a281aa62fbf08393c95f12ded9886ac212b3165f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720482"
---
# <a name="lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial"></a><span data-ttu-id="6c8a8-102">Lektion 3: Erstellen eines Warenkorbszenarios (Data Mining-Lernprogramm für Fortgeschrittene)</span><span class="sxs-lookup"><span data-stu-id="6c8a8-102">Lesson 3: Building a Market Basket Scenario (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="6c8a8-103">Die Marketingabteilung von [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] möchte die Unternehmenswebsite in Hinblick auf Cross-Selling-Möglichkeiten optimieren.</span><span class="sxs-lookup"><span data-stu-id="6c8a8-103">The marketing department of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] wants to improve the company Web site to promote cross-selling.</span></span> <span data-ttu-id="6c8a8-104">Als Teil des Websiteupdates soll die Möglichkeit bestehen, anhand von Produkten, die sich bereits im Onlinewarenkorb eines Kunden befinden, Produkte vorherzusagen, die der Kunde möglicherweise noch kaufen möchte.</span><span class="sxs-lookup"><span data-stu-id="6c8a8-104">As part of the site update, they would like the ability to predict products that a customer might want to purchase, based on the other products that are already in the customer's online shopping basket.</span></span> <span data-ttu-id="6c8a8-105">Die Marketingabteilung möchte außerdem das Kaufverhalten von Kunden besser verstehen, um die Website so zu gestalten, dass Artikel, die tendenziell zusammen gekauft werden, auch zusammen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6c8a8-105">The marketing department also wants to understand customer purchasing behavior better, so that they can design the Web site so that the items that tend to be purchased together appear together.</span></span> <span data-ttu-id="6c8a8-106">Die Marketingabteilung hat erfahren, dass Data Mining besonders nützlich für diese Art von *Warenkorbanalyse* ist, und bittet Sie, ein Data Mining-Modell zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="6c8a8-106">They have learned that data mining is especially useful for this kind of *market basket analysis* and have asked you to develop a data mining model.</span></span>  
  
 <span data-ttu-id="6c8a8-107">Nach Abschluss der Aufgaben in dieser Lektion verfügen Sie über ein Miningmodell, das Gruppen von Artikeln aus vergangenen Kundentransaktionen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="6c8a8-107">After you complete the tasks in this lesson, you will have a mining model that shows groups of items from historical customer transactions.</span></span> <span data-ttu-id="6c8a8-108">Außerdem können Sie das Miningmodell verwenden, um weitere Artikel vorherzusagen, die ein Kunde möglicherweise kaufen möchte.</span><span class="sxs-lookup"><span data-stu-id="6c8a8-108">Additionally, you can use the mining model to predict additional items that a customer may want to purchase.</span></span>  
  
 <span data-ttu-id="6c8a8-109">Zum Ausführen der Aufgaben in dieser Lektion verwenden Sie die Projekt Mappe und die Datenquelle, die Sie in der ersten Lektion des Data Mining-Lernprogramms für fortgeschrittene erstellt haben, [&#40;Analysis Services Data Mining-&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="6c8a8-109">To complete the tasks in this lesson, you will use the solution and data source that you created in the first lesson of the [Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span></span> <span data-ttu-id="6c8a8-110">Sie ändern diese Lösung, indem Sie eine Datenquellensicht hinzufügen, die Tabellen über den Kunden enthält, einschließlich einer geschachtelten Tabelle von Kundenbestellungen.</span><span class="sxs-lookup"><span data-stu-id="6c8a8-110">You will modify this solution by adding a data source view that contains tables about the customer, including a nested table of customer purchases.</span></span>  <span data-ttu-id="6c8a8-111">Anschließend erstellen Sie ein Miningmodell, dass den Microsoft Association Rules-Algorithmus verwendet, der für Warenkorbszenarien geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="6c8a8-111">You will then build a mining model that uses the Microsoft Association Rules algorithm, which is suited to market basket scenarios.</span></span>  
  
 <span data-ttu-id="6c8a8-112">Diese Lektion enthält die folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="6c8a8-112">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="6c8a8-113">Hinzufügen einer Datenquellen Sicht mit einer Reihe von Tabellen &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8a8-113">Adding a Data Source View with Nested Tables &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="6c8a8-114">Erstellen einer Market Basket-Struktur und eines Modells &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8a8-114">Creating a Market Basket Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-market-basket-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="6c8a8-115">Ändern und Verarbeiten des Market Basket-Modells &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8a8-115">Modifying and Processing the Market Basket Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/modify-process-market-basket-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="6c8a8-116">Erkunden des Market Basket-Modells &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8a8-116">Exploring the Market Basket Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-market-basket-models-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="6c8a8-117">Filtern einer geclusterte Tabelle in einem Mining Modell &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8a8-117">Filtering a Nested Table in a Mining Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/filtering-a-nested-table-in-a-mining-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="6c8a8-118">Vorhersagen von Zuordnungen &#40;Data&#41;Mining-Lernprogramms</span><span class="sxs-lookup"><span data-stu-id="6c8a8-118">Predicting Associations &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/predicting-associations-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="6c8a8-119">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="6c8a8-119">Next Task in Lesson</span></span>  
 [<span data-ttu-id="6c8a8-120">Hinzufügen einer Datenquellen Sicht mit einer Reihe von Tabellen &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8a8-120">Adding a Data Source View with Nested Tables &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="6c8a8-121">Alle Lektionen</span><span class="sxs-lookup"><span data-stu-id="6c8a8-121">All Lessons</span></span>  
 [<span data-ttu-id="6c8a8-122">Lektion 1: Erstellen der Data Mining-Lösung für fortgeschrittene &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8a8-122">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="6c8a8-123">Lektion 2: Erstellung eines Vorhersage Szenarios &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8a8-123">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 <span data-ttu-id="6c8a8-124">Lektion 3: Warenkorbszenario (Data Mining-Tutorial für Fortgeschrittene)</span><span class="sxs-lookup"><span data-stu-id="6c8a8-124">Lesson 3: Market Basket Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
 [<span data-ttu-id="6c8a8-125">Lektion 4: Entwickeln eines Sequence Clustering-Szenarios &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8a8-125">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 [<span data-ttu-id="6c8a8-126">Lektion 5: Erstellen von neuronalen Netzwerk- und logistischen Regressionsmodellen &#40;Data Mining-Tutorial für Fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8a8-126">Lesson 5: Building Neural Network and Logistic Regression Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-build-models-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="6c8a8-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6c8a8-127">See Also</span></span>  
 <span data-ttu-id="6c8a8-128">[Tutorial zu Data Mining-Grundlagen](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="6c8a8-128">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 <span data-ttu-id="6c8a8-129">[Lektion 2: Erstellung eines Vorhersage Szenarios &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="6c8a8-129">[Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="6c8a8-130">Lektion 4: Entwickeln eines Sequence Clustering-Szenarios &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="6c8a8-130">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
  
