---
title: Testen der Genauigkeit mit Lift Diagrammen (Lernprogramm zu Data Mining-Grundlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 822d414b-4a39-473f-80c3-53476e30655a
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 7a3dcdd1d1b78911f5ffd37a383532abdd4814c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718991"
---
# <a name="testing-accuracy-with-lift-charts-basic-data-mining-tutorial"></a><span data-ttu-id="d0b5a-102">Überprüfen der Genauigkeit mit Prognosegütediagrammen (Lernprogramm zu Data Mining-Grundlagen)</span><span class="sxs-lookup"><span data-stu-id="d0b5a-102">Testing Accuracy with Lift Charts (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="d0b5a-103">Auf der Registerkarte **Mining Genauigkeits Diagramm** des Data Mining-Designers können Sie berechnen, wie gut die einzelnen Modelle Vorhersagen treffen, und die Ergebnisse der einzelnen Modelle direkt mit den Ergebnissen der anderen Modelle vergleichen.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-103">On the **Mining Accuracy Chart** tab of Data Mining Designer, you can calculate how well each of your models makes predictions, and compare the results of each model directly against the results of the other models.</span></span> <span data-ttu-id="d0b5a-104">Diese Vergleichsmethode wird als *Lift Chart*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-104">This method of comparison is referred to as a *lift chart*.</span></span> <span data-ttu-id="d0b5a-105">In der Regel wird die Vorhersagegenauigkeit eines Miningmodells mit dem Lift oder der Klassifizierungsgenauigkeit gemessen.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-105">Typically, the predictive accuracy of a mining model is measured by either lift or classification accuracy.</span></span> <span data-ttu-id="d0b5a-106">In diesem Lernprogramm wird nur das Prognosegütediagramm verwendet.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-106">For this tutorial we will use the lift chart only.</span></span>  
  
 <span data-ttu-id="d0b5a-107">Im Rahmen dieses Themas führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="d0b5a-107">In this topic, you will perform the following tasks:</span></span>  
  
-   [<span data-ttu-id="d0b5a-108">Auswählen der Eingabedaten</span><span class="sxs-lookup"><span data-stu-id="d0b5a-108">Choose the Input Data</span></span>](#BKMK_InputData)  
  
-   [<span data-ttu-id="d0b5a-109">Konfigurieren von Parametern für das Genauigkeitsdiagramm</span><span class="sxs-lookup"><span data-stu-id="d0b5a-109">Configure Accuracy Chart Parameters</span></span>](#BKMK_Selecting)  
  
##  <a name="choosing-the-input-data"></a><a name="BKMK_InputData"></a><span data-ttu-id="d0b5a-110">Auswählen der Eingabedaten</span><span class="sxs-lookup"><span data-stu-id="d0b5a-110">Choosing the Input Data</span></span>  
 <span data-ttu-id="d0b5a-111">Der erste Schritt beim Testen der Genauigkeit von Miningmodellen ist die Auswahl der Datenquelle, die Sie für den Test verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-111">The first step in testing the accuracy of your mining models is to select the data source that you will use for testing.</span></span> <span data-ttu-id="d0b5a-112">Sie überprüfen die Leistung der Modelle anhand der Testdaten und verwenden dieses anschließend mit externen Daten.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-112">You will test how well the models perform against your testing data and then you will use them with external data.</span></span>  
  
#### <a name="to-select-the-data-set"></a><span data-ttu-id="d0b5a-113">So wählen Sie das Dataset aus</span><span class="sxs-lookup"><span data-stu-id="d0b5a-113">To select the data set</span></span>  
  
1.  <span data-ttu-id="d0b5a-114">Wechseln Sie in zur Registerkarte **Mining Genauigkeits Diagramm** im Data Mining-Designer, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] und wählen Sie die Registerkarte **Eingabeauswahl** aus.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-114">Switch to the **Mining Accuracy Chart** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and select the **Input Selection** tab.</span></span>  
  
2.  <span data-ttu-id="d0b5a-115">Wählen Sie im Gruppenfeld Dataset **auswählen, das für das Genauigkeits Diagramm verwendet werden soll** die Option **Testfälle für Mining Struktur verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-115">In the **Select data set to be used for Accuracy Chart** group box, select **Use mining structure test cases**.</span></span> <span data-ttu-id="d0b5a-116">Dies sind die Testdaten, die Sie beim Erstellen der Miningstruktur vorgesehen haben.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-116">This is the testing data that you set aside when you created the mining structure.</span></span>  
  
     <span data-ttu-id="d0b5a-117">Weitere Informationen zu den anderen Optionen finden Sie unter [Auswählen eines Genauigkeits Diagramm Typs und Festlegen von Diagramm Optionen](../../2014/analysis-services/data-mining/choose-an-accuracy-chart-type-and-set-chart-options.md).</span><span class="sxs-lookup"><span data-stu-id="d0b5a-117">For more information on the other options, see [Choose an Accuracy Chart Type and Set Chart Options](../../2014/analysis-services/data-mining/choose-an-accuracy-chart-type-and-set-chart-options.md).</span></span>  
  
##  <a name="setting-accuracy-chart-parameters"></a><a name="BKMK_Selecting"></a><span data-ttu-id="d0b5a-118">Festlegen von Genauigkeits Diagramm Parametern</span><span class="sxs-lookup"><span data-stu-id="d0b5a-118">Setting Accuracy Chart Parameters</span></span>  
 <span data-ttu-id="d0b5a-119">Beim Erstellen eines Genauigkeitsdiagramms müssen Sie drei Entscheidungen treffen:</span><span class="sxs-lookup"><span data-stu-id="d0b5a-119">To create an accuracy chart, you must define three things:</span></span>  
  
-   <span data-ttu-id="d0b5a-120">Welche Modelle sollen in das Genauigkeitsdiagramm eingeschlossen werden?</span><span class="sxs-lookup"><span data-stu-id="d0b5a-120">Which models should you include in the accuracy chart?</span></span>  
  
-   <span data-ttu-id="d0b5a-121">Welches vorhersagbare Attribut soll gemessen werden?</span><span class="sxs-lookup"><span data-stu-id="d0b5a-121">Which predictable attribute do you want to measure?</span></span> <span data-ttu-id="d0b5a-122">Einige Modelle verfügen u. U. über mehrere Ziele, allerdings kann mit jedem Diagramm jeweils nur ein Ergebnis gemessen werden.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-122">Some models might have multiple targets, but each chart can measure only one outcome at a time.</span></span>  
  
     <span data-ttu-id="d0b5a-123">Wenn Sie eine Spalte als **vorhersagbaren Spaltennamen** in einem Genauigkeits Diagramm verwenden möchten, müssen die Spalten den Verwendungstyp `Predict` oder aufweisen `Predict Only` .</span><span class="sxs-lookup"><span data-stu-id="d0b5a-123">To use a column as the **Predictable Column Name** in an accuracy chart, the columns must have the usage type of `Predict` or `Predict Only`.</span></span> <span data-ttu-id="d0b5a-124">Darüber hinaus muss der Inhaltstyp der Zielspalte entweder `Discrete` oder `Discretized` lauten.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-124">Also, the content type of the target column must be either `Discrete` or `Discretized`.</span></span> <span data-ttu-id="d0b5a-125">Dies bedeutet, dass die Genauigkeit nicht unter Verwendung kontinuierlicher numerischer Ergebnisse mit dem Prognosegütediagramm gemessen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-125">In other words, you cannot measure accuracy against continuous numeric outputs using the lift chart.</span></span>  
  
-   <span data-ttu-id="d0b5a-126">Möchten Sie die allgemeine Genauigkeit des Modells oder seine Genauigkeit bei der Vorhersage eines bestimmten Werts Messen (z. b. [Bike Buyer] = ' yes ')</span><span class="sxs-lookup"><span data-stu-id="d0b5a-126">Do you want to measure the model's general accuracy, or its accuracy  in predicting a particular value (such as [Bike Buyer] = 'Yes')</span></span>  
  
#### <a name="to-generate-the-lift-chart"></a><span data-ttu-id="d0b5a-127">So erstellen Sie das Prognosegütediagramm</span><span class="sxs-lookup"><span data-stu-id="d0b5a-127">To generate the lift chart</span></span>  
  
1.  <span data-ttu-id="d0b5a-128">Aktivieren Sie auf der Registerkarte **Eingabeauswahl** des Data Mining-Designers unter **Wählen Sie die vorhersagbaren Mining Modell Spalten**aus, die im Prognose Prognose Diagramm angezeigt werden sollen das Kontrollkästchen **Vorhersage Spalten und-Werte synchronisieren**.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-128">On the **Input Selection** tab of Data Mining Designer, under **Select predictable mining model columns to show in the lift chart**, select the checkbox for **Synchronize Prediction Columns and Values**.</span></span>  
  
2.  <span data-ttu-id="d0b5a-129">Überprüfen Sie in der Spalte **Name der vorhersagbaren Spalte** , ob **Bike Buyer** für jedes Modell ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-129">In the **Predictable Column Name** column, verify that **Bike Buyer** is selected for each model.</span></span>  
  
3.  <span data-ttu-id="d0b5a-130">Wählen Sie in der Spalte **anzeigen** die einzelnen Modelle aus.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-130">In the **Show** column, select each of the models.</span></span>  
  
     <span data-ttu-id="d0b5a-131">Standardmäßig werden alle Modelle in der Miningstruktur ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-131">By default, all the models in the mining structure are selected.</span></span> <span data-ttu-id="d0b5a-132">Sie können angeben, dass ein Modell nicht mit aufgenommen werden soll. Behalten Sie jedoch für dieses Lernprogramm die Auswahl aller Modelle bei.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-132">You can decide not to include a model, but for this tutorial leave all the models selected.</span></span>  
  
4.  <span data-ttu-id="d0b5a-133">Wählen Sie in der Spalte **Wert vorhersagen den Wert** **1**aus.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-133">In the **Predict Value** column, select **1**.</span></span> <span data-ttu-id="d0b5a-134">Der gleiche Wert wird automatisch für jedes Modell eingegeben, das die gleiche vorhersagbare Spalte besitzt.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-134">The same value is automatically filled in for each model that has the same predictable column.</span></span>  
  
5.  <span data-ttu-id="d0b5a-135">Wählen Sie die Registerkarte **Lift Chart** aus.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-135">Select the **Lift Chart** tab.</span></span>  
  
     <span data-ttu-id="d0b5a-136">Wenn Sie auf die Registerkarte klicken, wird eine Vorhersageabfrage ausgeführt, um Vorhersagen für die Testdaten abzurufen. Anschließend werden die Ergebnisse mit den bekannten Werten verglichen.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-136">When you click the tab, a prediction query is executed to get predictions for the test data, and the results are compared against the known values.</span></span> <span data-ttu-id="d0b5a-137">Die Ergebnisse werden im Diagramm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-137">The results are plotted on the graph.</span></span>  
  
     <span data-ttu-id="d0b5a-138">Wenn Sie mithilfe der Option **Wert vorhersagen** ein bestimmtes Zielergebnis angegeben haben, werden die Ergebnisse zufälliger Vermutungen und die Ergebnisse eines idealen Modells durch das Prognose Diagramm dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-138">If you specified a particular target outcome using the **Predict Value** option, the lift chart plots the results of random guesses and the results of an ideal model.</span></span>  
  
    -   <span data-ttu-id="d0b5a-139">Die Zufallsvorhersagelinie zeigt, wie genau das Modell wäre, wenn keine Informationsdaten für die Vorhersagen bereitgestellt würden: d. h. eine Aufteilung von 50:50 zwischen zwei Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-139">The random guess line shows how accurate the model would be without using any data to inform its predictions: that is, a 50-50 split between two outcomes.</span></span> <span data-ttu-id="d0b5a-140">Mithilfe des Prognosegütediagramms kann visuell dargestellt werden, wie viel besser das Modell im Vergleich zu einer Zufallsvorhersage abschneidet.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-140">The lift chart helps you visualize how much better your model performs in comparison to a random guess.</span></span>  
  
    -   <span data-ttu-id="d0b5a-141">Die Linie für das ideale Modell stellt die Obergrenze der Genauigkeit dar.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-141">The ideal model line represents the upper bound of accuracy.</span></span> <span data-ttu-id="d0b5a-142">Sie zeigt den maximal möglichen Nutzen, den Sie erzielen könnten, wenn die Modellvorhersage immer genau wäre.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-142">It shows you the maximum possible benefit you could achieve if your model always predicted accurately.</span></span>  
  
     <span data-ttu-id="d0b5a-143">Die von Ihnen erstellten Miningmodelle bewegen sich normalerweise zwischen diesen beiden Extremen.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-143">The mining models you created will usually fall between these two extremes.</span></span> <span data-ttu-id="d0b5a-144">Jede Verbesserung der Zufalls Vorhersage wird als *Lift*betrachtet.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-144">Any improvement from the random guess is considered to be *lift*.</span></span>  
  
6.  <span data-ttu-id="d0b5a-145">Verwenden Sie die Legende, um die farbigen Zeilen zu identifizieren, die das Idealmodell und das Zufallsvorhersagemodell darstellen.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-145">Use the legend to locate the colored lines representing the Ideal Model and the Random Guess Model.</span></span>  
  
     <span data-ttu-id="d0b5a-146">Sie werden feststellen, dass das `TM_Decision_Tree` Modell den größten Lift bietet und dabei sowohl die Clustering-als auch Naive Bayes-Modelle bietet.</span><span class="sxs-lookup"><span data-stu-id="d0b5a-146">You'll notice that the `TM_Decision_Tree` model provides the greatest lift,  outperforming both the Clustering and Naive Bayes models.</span></span>  
  
 <span data-ttu-id="d0b5a-147">Eine ausführliche Erläuterung eines in dieser Lektion erstellten Lift Diagramms finden Sie unter [Lift Chart &#40;Analysis Services-Data Mining&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="d0b5a-147">For an in-depth explanation of a lift chart similar to the one created in this lesson, see [Lift Chart &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md).</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="d0b5a-148">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="d0b5a-148">Next Task in Lesson</span></span>  
 [<span data-ttu-id="d0b5a-149">Testen eines gefilterten Modells &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="d0b5a-149">Testing a Filtered Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-a-filtered-model-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="d0b5a-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0b5a-150">See Also</span></span>  
 <span data-ttu-id="d0b5a-151">[Lift Chart &#40;Analysis Services-Data Mining-&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="d0b5a-151">[Lift Chart &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/lift-chart-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="d0b5a-152">Registerkarte "Lift Chart" &#40;Mining Genauigkeits Diagramm Ansicht&#41;</span><span class="sxs-lookup"><span data-stu-id="d0b5a-152">Lift Chart Tab &#40;Mining Accuracy Chart View&#41;</span></span>](../../2014/analysis-services/lift-chart-tab-mining-accuracy-chart-view.md)  
  
  
