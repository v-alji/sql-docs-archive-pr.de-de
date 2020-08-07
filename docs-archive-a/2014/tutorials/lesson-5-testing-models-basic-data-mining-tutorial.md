---
title: 'Lektion 5: Testen von Modellen (Lernprogramm zu Data Mining-Grundlagen) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e9a7ddcf-2b01-485f-bbb5-62638b303bc6
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: fcfd9a9e90d9c6800af4dfd1599bbdd62d9520ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719066"
---
# <a name="lesson-5-testing-models-basic-data-mining-tutorial"></a><span data-ttu-id="4cfd9-102">Lektion 5: Testen von Modellen (Lernprogramm zu Data Mining-Grundlagen)</span><span class="sxs-lookup"><span data-stu-id="4cfd9-102">Lesson 5: Testing Models (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="4cfd9-103">Nachdem Sie das Modell mit dem Trainingssatz für das Targeted Mailing-Szenario verarbeitet haben, können Sie die Modelle mit dem Testsatz überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4cfd9-103">Now that you have processed the model by using the targeted mailing scenario training set, you will test your models against the testing set.</span></span> <span data-ttu-id="4cfd9-104">Die Überprüfung ist ein wichtiger Schritt im Data Mining-Prozess.</span><span class="sxs-lookup"><span data-stu-id="4cfd9-104">Validation is an important step in the data mining process.</span></span> <span data-ttu-id="4cfd9-105">Sie sollten wissen, welche Leistung Ihre Miningmodelle für Targeted Mailing mit echten Daten erzielen, bevor Sie die Modelle in Ihrer Produktionsumgebung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4cfd9-105">Knowing how well your targeted mailing mining models perform against real data is important before you deploy the models into a production environment.</span></span>  
  
 <span data-ttu-id="4cfd9-106">Da die Daten im Testsatz bereits bekannte Werte für das Fahrradkaufverhalten enthalten, ist es einfach, die Vorhersagegenauigkeit des Modells zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="4cfd9-106">Because the data in the testing set already contains known values for bike buying, it is easy to determine whether the model's predictions are correct.</span></span> <span data-ttu-id="4cfd9-107">Das Modell mit den besten Ergebnissen wird von der Marketingabteilung von [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] zur Identifizierung von Kunden für die Target Mailing-Kampagne verwendet.</span><span class="sxs-lookup"><span data-stu-id="4cfd9-107">The model that performs the best will be used by the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] marketing department to identify the customers for their targeted mailing campaign.</span></span>  
  
 <span data-ttu-id="4cfd9-108">In dieser Lektion überprüfen Sie die Modelle mithilfe mehrerer Methoden:</span><span class="sxs-lookup"><span data-stu-id="4cfd9-108">In this lesson you will validate your models using multiple methods:</span></span>  
  
1.  <span data-ttu-id="4cfd9-109">Sie treffen Vorhersagen für den Testsatz, um zu sehen, wie genau das Modell für bekannte Ergebnisse ist.</span><span class="sxs-lookup"><span data-stu-id="4cfd9-109">You'll make predictions against the testing set to see how accurate the model is on known results.</span></span> <span data-ttu-id="4cfd9-110">Sie verwenden ein *Lift Diagramm* , um seine Effektivität zu messen.</span><span class="sxs-lookup"><span data-stu-id="4cfd9-110">You'll use a *lift chart* to measure its effectiveness.</span></span>  
  
     [<span data-ttu-id="4cfd9-111">Überprüfen der Genauigkeit mit Prognosegütediagrammen &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="4cfd9-111">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
2.  <span data-ttu-id="4cfd9-112">Anschließend testen Sie die Modelle mit einer gefilterten Teilmenge der Daten.</span><span class="sxs-lookup"><span data-stu-id="4cfd9-112">You will test your models on a filtered subset of the data.</span></span> <span data-ttu-id="4cfd9-113">Sie können mehrere Modelle im selben Prognosegütediagramm vergleichen.</span><span class="sxs-lookup"><span data-stu-id="4cfd9-113">You can compare multiple models in the same lift chart.</span></span>  
  
     [<span data-ttu-id="4cfd9-114">Testen eines gefilterten Modells &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="4cfd9-114">Testing a Filtered Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-a-filtered-model-basic-data-mining-tutorial.md)  
  
 <span data-ttu-id="4cfd9-115">Weitere Informationen zur Modell Validierung im Allgemeinen finden Sie unter [Data Mining-Konzepte](../../2014/analysis-services/data-mining/data-mining-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="4cfd9-115">For more information about how model validation in general, see [Data Mining Concepts](../../2014/analysis-services/data-mining/data-mining-concepts.md).</span></span>  
  
## <a name="first-task-in-lesson"></a><span data-ttu-id="4cfd9-116">Erste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="4cfd9-116">First Task in Lesson</span></span>  
 [<span data-ttu-id="4cfd9-117">Überprüfen der Genauigkeit mit Prognosegütediagrammen &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="4cfd9-117">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
## <a name="previous-lesson"></a><span data-ttu-id="4cfd9-118">Vorherige Lektion</span><span class="sxs-lookup"><span data-stu-id="4cfd9-118">Previous Lesson</span></span>  
 [<span data-ttu-id="4cfd9-119">Lektion 4: Untersuchen der Ziel-Mailing-Modelle &#40;grundlegenden Data Mining-Lernprogramm&#41;</span><span class="sxs-lookup"><span data-stu-id="4cfd9-119">Lesson 4: Exploring the Targeted Mailing Models &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-4-exploring-the-targeted-mailing-models-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="4cfd9-120">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="4cfd9-120">Next Lesson</span></span>  
 [<span data-ttu-id="4cfd9-121">Lektion 6: Erstellen und Verwenden von Vorhersagen &#40;Tutorial zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="4cfd9-121">Lesson 6: Creating and Working with Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="4cfd9-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4cfd9-122">See Also</span></span>  
 <span data-ttu-id="4cfd9-123">[Registerkarte "Lift Chart" &#40;Mining Genauigkeits Diagramm Ansicht&#41;](../../2014/analysis-services/lift-chart-tab-mining-accuracy-chart-view.md) </span><span class="sxs-lookup"><span data-stu-id="4cfd9-123">[Lift Chart Tab &#40;Mining Accuracy Chart View&#41;](../../2014/analysis-services/lift-chart-tab-mining-accuracy-chart-view.md) </span></span>  
 <span data-ttu-id="4cfd9-124">[Lift Chart &#40;Analysis Services-Data Mining-&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="4cfd9-124">[Lift Chart &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="4cfd9-125">[Testen und validieren &#40;Data Mining-&#41;](../../2014/analysis-services/data-mining/testing-and-validation-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="4cfd9-125">[Testing and Validation &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/testing-and-validation-data-mining.md) </span></span>  
 <span data-ttu-id="4cfd9-126">[Klassifizierungs Matrix-Registerkarte &#40;Mining Genauigkeits Diagramm Ansicht&#41;](../../2014/analysis-services/classification-matrix-tab-mining-accuracy-chart-view.md) </span><span class="sxs-lookup"><span data-stu-id="4cfd9-126">[Classification Matrix Tab &#40;Mining Accuracy Chart View&#41;](../../2014/analysis-services/classification-matrix-tab-mining-accuracy-chart-view.md) </span></span>  
 [<span data-ttu-id="4cfd9-127">Klassifikationsmatrix &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="4cfd9-127">Classification Matrix &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/classification-matrix-analysis-services-data-mining.md)  
  
  
