---
title: 'Lektion 5: aufbauen von neuronalen Netzwerk-und logistischen Regressionsmodellen (Data Mining-Tutorial für Fortgeschrittene) Microsoft-Dokumentation'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- logistic regression [Analysis Services]
- data mining [Analysis Services], tutorials
- neural networks
- tutorials [Data Mining]
- neural network model [Analysis Services]
ms.assetid: 42c3701a-1fd2-44ff-b7de-377345bbbd6b
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a8c9fcf0380582f15fa2bf30d6fdeb97bb2ab1fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616865"
---
# <a name="lesson-5-building-neural-network-and-logistic-regression-models-intermediate-data-mining-tutorial"></a><span data-ttu-id="117f1-102">Lektion 5: Erstellen von neuronalen Netzwerk- und logistischen Regressionsmodellen (Data Mining-Lernprogramm für Fortgeschrittene)</span><span class="sxs-lookup"><span data-stu-id="117f1-102">Lesson 5: Building Neural Network and Logistic Regression Models (Intermediate Data Mining Tutorial)</span></span>
  
  
 <span data-ttu-id="117f1-103">Die Betriebsabteilung von [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] arbeitet daran, die Kundenzufriedenheit bezüglich des Callcenters zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="117f1-103">The Operations department of [!INCLUDE[ssSampleDBCoShort](../includes/sssampledbcoshort-md.md)] is engaged in a project to improve customer satisfaction with their call center.</span></span> <span data-ttu-id="117f1-104">Ein Drittanbieter wurde mit der Führung des Callcenters und der Erstellung von Berichten zu Metriken bezüglich der Effektivität des Callcenters beauftragt. Ihre Aufgabe ist es, einige vorläufige durch den Drittanbieter bereitgestellte Daten zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="117f1-104">They hired a vendor to manage the call center and to report metrics on call center effectiveness, and have asked you to analyze some preliminary data provided by the vendor.</span></span> <span data-ttu-id="117f1-105">Ihr Auftraggeber möchte wissen, ob es interessante Ergebnisse gibt.</span><span class="sxs-lookup"><span data-stu-id="117f1-105">They want to know if there are any interesting findings.</span></span> <span data-ttu-id="117f1-106">Insbesondere ist interessant, ob die Daten Rückschlüsse auf Probleme mit der Personalbesetzung zulassen oder Möglichkeiten aufzeigen, die Kundenzufriedenheit zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="117f1-106">In particular, they would like to know if the data suggests any staffing problems with staffing or ways to improve customer satisfaction.</span></span>  
  
 <span data-ttu-id="117f1-107">Das Dataset ist klein und umfasst nur einen Zeitraum von 30 Tagen im Betrieb des Callcenters.</span><span class="sxs-lookup"><span data-stu-id="117f1-107">The data set is small and covers only a 30-day period in the operation of the call center.</span></span> <span data-ttu-id="117f1-108">Die Daten verfolgen die Anzahl der neuen und erfahrenen Operatoren in jeder Schicht, die Anzahl der eingehenden Aufrufe, die Anzahl von Bestellungen und zu lösenden Problemen sowie die durchschnittlich Wartezeit eines Kunden, bis ein Operator auf einen Aufruf reagiert.</span><span class="sxs-lookup"><span data-stu-id="117f1-108">The data tracks the number of new and experienced operators in each shift, the number of incoming calls, the number of orders as well as issues that must be resolved, and the average time a customer waits for someone to respond to a call.</span></span> <span data-ttu-id="117f1-109">Die Daten enthalten zudem eine Dienstqualitätsmetrik auf Grundlage der *Abbruchrate*, die ein Indikator der Kundenfrustration ist.</span><span class="sxs-lookup"><span data-stu-id="117f1-109">The data also includes a service quality metric based on *abandon rate*, which is an indicator of customer frustration.</span></span>  
  
 <span data-ttu-id="117f1-110">Da Sie im Voraus keine bestimmten Ergebnisse von der Datenanalyse erwarten, beschließen Sie, mithilfe eines neuronalen Netzwerkmodells die Daten auf mögliche Korrelationen zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="117f1-110">Because you do not have any prior expectations about what the data will show, you decide to use a neural network model to explore possible correlations.</span></span> <span data-ttu-id="117f1-111">Neuronale Netzwerkmodelle werden oft zum Durchsuchen von Daten verwendet, da mit diesen komplexe Beziehungen zwischen vielen Eingaben und Ausgaben analysiert werden können.</span><span class="sxs-lookup"><span data-stu-id="117f1-111">Neural network models are often used for exploration because they can analyze complex relationships between many inputs and outputs.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="117f1-112">Lernziele</span><span class="sxs-lookup"><span data-stu-id="117f1-112">What You Will Learn</span></span>  
 <span data-ttu-id="117f1-113">In dieser Lektion verwenden Sie den Neural Network-Algorithmus, um ein Modell zu erstellen, das Sie und das Betriebsteam verwenden können, um die Trends in den Daten zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="117f1-113">In this lesson, you will use the neural network algorithm to build a model that you and the Operations team can use to understand the trends in the data.</span></span> <span data-ttu-id="117f1-114">Als Teil dieser Lektion versuchen Sie, die folgenden Fragen zu beantworten:</span><span class="sxs-lookup"><span data-stu-id="117f1-114">As part of this lesson, you will try to answer the following questions:</span></span>  
  
-   <span data-ttu-id="117f1-115">Welche Faktoren beeinflussen die Kundenzufriedenheit?</span><span class="sxs-lookup"><span data-stu-id="117f1-115">What factors affect customer satisfaction?</span></span>  
  
-   <span data-ttu-id="117f1-116">Wie kann das Callcenter die Dienstqualität verbessern?</span><span class="sxs-lookup"><span data-stu-id="117f1-116">What can the call center do to improve service quality?</span></span>  
  
 <span data-ttu-id="117f1-117">Auf Grundlage der Ergebnisse erstellen Sie dann ein logistisches Regressionsmodell, das Sie für Vorhersagen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="117f1-117">Based on the results, you will then build a logistic regression model that you can use for predictions.</span></span> <span data-ttu-id="117f1-118">Die Vorhersagen werden vom Betriebsteam für die Betriebsplanung des Callcenters verwendet.</span><span class="sxs-lookup"><span data-stu-id="117f1-118">The predictions will be used by the Operations team as an aid in planning call center operation.</span></span>  
  
 <span data-ttu-id="117f1-119">Diese Lektion enthält die folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="117f1-119">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="117f1-120">Hinzufügen einer Datenquellen Sicht für callcenterdata &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="117f1-120">Adding a Data Source View for Call Center Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/add-data-source-view-call-center-data-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="117f1-121">Erstellen einer neuronalen Netzwerkstruktur und eines Modells &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="117f1-121">Creating a Neural Network Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-neural-network-structure-and-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="117f1-122">Untersuchen des Callcentermodells &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="117f1-122">Exploring the Call Center Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-call-center-model-intermediate-data-mining-tutorial.md)  
  
-   [<span data-ttu-id="117f1-123">Hinzufügen eines logistischen Regressionsmodells zur Callcenterstruktur &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="117f1-123">Adding a Logistic Regression Model to the Call Center Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/add-logistic-regression-model-to-call-center-intermediate-data-mining.md)  
  
-   [<span data-ttu-id="117f1-124">Erstellen von Vorhersagen für die Callcentermodelle &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="117f1-124">Creating Predictions for the Call Center Models &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/create-predictions-call-center-models-intermediate-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="117f1-125">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="117f1-125">Next Task in Lesson</span></span>  
 [<span data-ttu-id="117f1-126">Hinzufügen einer Datenquellen Sicht für callcenterdata &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="117f1-126">Adding a Data Source View for Call Center Data &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/add-data-source-view-call-center-data-intermediate-data-mining.md)  
  
## <a name="all-lessons"></a><span data-ttu-id="117f1-127">Alle Lektionen</span><span class="sxs-lookup"><span data-stu-id="117f1-127">All Lessons</span></span>  
 [<span data-ttu-id="117f1-128">Lektion 1: Erstellen der Data Mining-Lösung für fortgeschrittene &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="117f1-128">Lesson 1: Creating the Intermediate Data Mining Solution &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-1-create-solution-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="117f1-129">Lektion 2: Erstellung eines Vorhersage Szenarios &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="117f1-129">Lesson 2: Building a Forecasting Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-forecasting-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="117f1-130">Lektion 3: Erstellen eines Warenkorbszenarios &#40;Data Mining-Tutorial für Fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="117f1-130">Lesson 3: Building a Market Basket Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-3-building-a-market-basket-scenario-intermediate-data-mining-tutorial.md)  
  
 [<span data-ttu-id="117f1-131">Lektion 4: Entwickeln eines Sequence Clustering-Szenarios &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="117f1-131">Lesson 4: Building a Sequence Clustering Scenario &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-build-sequence-clustering-scenario-intermediate-data-mining.md)  
  
 <span data-ttu-id="117f1-132">Lektion 5: Neuronale Netzwerk- und logistische Regressionsszenarios (Data Mining-Tutorial für Fortgeschrittene)</span><span class="sxs-lookup"><span data-stu-id="117f1-132">Lesson 5: Neural Network and Logistic Regression Scenario (Intermediate Data Mining Tutorial)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="117f1-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="117f1-133">See Also</span></span>  
 <span data-ttu-id="117f1-134">[Tutorial zu Data Mining-Grundlagen](../../2014/tutorials/basic-data-mining-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="117f1-134">[Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md) </span></span>  
 [<span data-ttu-id="117f1-135">Data Mining-Lernprogramm für fortgeschrittene &#40;Analysis Services-Data Mining-&#41;</span><span class="sxs-lookup"><span data-stu-id="117f1-135">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
  
