---
title: 'Lektion 6: Erstellen und arbeiten mit Vorhersagen (Lernprogramm zu Data Mining-Grundlagen) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b213cb58-2c40-4c89-b08b-d3c36a4afad3
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d0a8bfdf83e96622a19ac72490e8602d12afc9df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615711"
---
# <a name="lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial"></a><span data-ttu-id="b7edd-102">Lektion 6: Erstellen und Verwenden von Vorhersagen (Lernprogramm zu Data Mining-Grundlagen)</span><span class="sxs-lookup"><span data-stu-id="b7edd-102">Lesson 6: Creating and Working with Predictions (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="b7edd-103">Sie haben die Data Mining-Modelle, die Sie erstellt haben, trainiert, getestet und untersucht.</span><span class="sxs-lookup"><span data-stu-id="b7edd-103">You have trained, tested, and explored the data mining models you created.</span></span> <span data-ttu-id="b7edd-104">Jetzt können Sie mithilfe der Modelle ermitteln, welche Personen sich am wahrscheinlichsten von der neuen zielgerichteten Mailingkampagne angesprochen fühlen.</span><span class="sxs-lookup"><span data-stu-id="b7edd-104">Now you are ready to use the models to identify the people most likely to respond to the new targeted mailing campaign.</span></span>  
  
 <span data-ttu-id="b7edd-105">In dieser Lektion erstellen Sie eine Abfrage, um vorherzusagen, welche Kunden am wahrscheinlichsten ein Fahrrad kaufen werden.</span><span class="sxs-lookup"><span data-stu-id="b7edd-105">In this lesson you will create a query to predict which customers are most likely to purchase a bike.</span></span> <span data-ttu-id="b7edd-106">Außerdem ermitteln Sie, wie *wahrscheinlich* es ist, dass die Vorhersage zutrifft. Auf dieser Grundlage kann die Marketingabteilung entscheiden, ob die Vorhersage verwendbar ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="b7edd-106">You will also retrieve the *probability* that the prediction is correct, so the marketing department can decide whether to you can decide whether to use the prediction or not.</span></span>  
  
 <span data-ttu-id="b7edd-107">Nachdem Sie die Kunden identifiziert haben, die mit hoher Wahrscheinlichkeit ein Fahrrad kaufen, führen Sie einen Drillthrough zu den Details der Fälle im Miningmodell aus, um die Namen und Kontaktinformationen der Kunden abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b7edd-107">Once you have identified customers with a high probability of purchasing a bike, you will drill through to the details of the cases in the mining model to retrieve names and contact information for these customers.</span></span>  
  
 <span data-ttu-id="b7edd-108">Diese Lektion enthält die folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="b7edd-108">This lesson contains the following topics:</span></span>  
  
 [<span data-ttu-id="b7edd-109">Erstellen von Vorhersagen &#40;Tutorial zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="b7edd-109">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="b7edd-110">Verwenden von Drillthrough für Strukturdaten &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="b7edd-110">Using Drillthrough on Structure Data &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/using-drillthrough-on-structure-data-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="b7edd-111">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="b7edd-111">Next Lesson</span></span>  
 [<span data-ttu-id="b7edd-112">Data Mining-Lernprogramm für fortgeschrittene &#40;Analysis Services-Data Mining-&#41;</span><span class="sxs-lookup"><span data-stu-id="b7edd-112">Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="b7edd-113">Vorherige Lektion</span><span class="sxs-lookup"><span data-stu-id="b7edd-113">Previous Lesson</span></span>  
 [<span data-ttu-id="b7edd-114">Lektion 5: Testen von Modellen &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="b7edd-114">Lesson 5: Testing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-5-testing-models-basic-data-mining-tutorial.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="b7edd-115">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="b7edd-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="b7edd-116">Erstellen von Vorhersagen &#40;Tutorial zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="b7edd-116">Creating Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="b7edd-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7edd-117">See Also</span></span>  
 <span data-ttu-id="b7edd-118">[Mining Modell Inhalt von Entscheidungsstruktur Modellen &#40;Analysis Services Data Mining-&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-decision-tree-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="b7edd-118">[Mining Model Content for Decision Tree Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-decision-tree-models-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="b7edd-119">erstellt eine Vorhersage mithilfe des Generators für Vorhersageabfragen</span><span class="sxs-lookup"><span data-stu-id="b7edd-119">Create a Prediction Query Using the Prediction Query Builder</span></span>](../../2014/analysis-services/data-mining/create-a-prediction-query-using-the-prediction-query-builder.md)  
  
  
