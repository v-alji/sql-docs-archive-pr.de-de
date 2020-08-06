---
title: Registerkarte "Kreuz Validierung" (Mining Genauigkeits Diagramm-Sicht) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.crossvalidation.f1
ms.assetid: bd215a68-1ad7-4046-9c44-ec8e2be13a64
author: minewiskan
ms.author: owend
ms.openlocfilehash: 867bd6d1abffb29ec3eb2a8a78e562e5cbcc5b29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616858"
---
# <a name="cross-validation-tab-mining-accuracy-chart-view"></a><span data-ttu-id="4efeb-102">Übergreifende Überprüfung (Registerkarte, Mininggenauigkeitsdiagramm-Sicht)</span><span class="sxs-lookup"><span data-stu-id="4efeb-102">Cross-Validation Tab (Mining Accuracy Chart View)</span></span>
  <span data-ttu-id="4efeb-103">Mithilfe der übergreifenden Überprüfung können Sie eine Miningstruktur in Querschnitte partitionieren und Modelle anhand der einzelnen Querschnitte iterativ trainieren und testen.</span><span class="sxs-lookup"><span data-stu-id="4efeb-103">Cross-validation lets you partition a mining structure into cross-sections and iteratively train and test models against each cross-section.</span></span> <span data-ttu-id="4efeb-104">Sie geben eine Anzahl von Aufteilungen für die Daten an. Die einzelnen Aufteilungen werden der Reihe nach als Testdaten verwendet, während mit den jeweils verbleibenden Daten ein neues Modell trainiert wird.</span><span class="sxs-lookup"><span data-stu-id="4efeb-104">You specify a number of folds to divide the data into, and each fold is used in turn as the test data, whereas the remaining data is used to train a new model.</span></span> [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="4efeb-105">generiert dann eine Gruppe vorgegebener Genauigkeitsmetriken für jedes Modell.</span><span class="sxs-lookup"><span data-stu-id="4efeb-105">then generates a set of standard accuracy metrics for each model.</span></span> <span data-ttu-id="4efeb-106">Durch den Vergleich der Metriken für die für die einzelnen Querschnitte generierten Modelle erhalten Sie Aufschluss über die Zuverlässigkeit des Miningmodells für das ganze Dataset.</span><span class="sxs-lookup"><span data-stu-id="4efeb-106">By comparing the metrics for the models generated for each cross-section, you can get a good idea of how reliable the mining model is for the whole data set.</span></span>  
  
 <span data-ttu-id="4efeb-107">Weitere Informationen finden Sie unter [Kreuzvalidierung &#40;Analysis Services – Data Mining&#41;](data-mining/cross-validation-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="4efeb-107">For more information, see [Cross-Validation &#40;Analysis Services - Data Mining&#41;](data-mining/cross-validation-analysis-services-data-mining.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4efeb-108">Die übergreifende Überprüfung kann nicht bei Modellen verwendet werden, die mithilfe des [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series-Algorithmus oder des [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering-Algorithmus erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="4efeb-108">Cross-validation cannot be used with models that were built by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Time Series algorithm or the [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering algorithm.</span></span> <span data-ttu-id="4efeb-109">Wenn Sie den Bericht für eine Miningstruktur mit diesen Typen von Modellen ausführen, werden die Modelle im Bericht nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="4efeb-109">If you run the report on a mining structure that contains these types of models, the models will not be included in the report.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="4efeb-110">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="4efeb-110">Task List</span></span>  
  
-   <span data-ttu-id="4efeb-111">Geben Sie die Anzahl von Aufteilungen an.</span><span class="sxs-lookup"><span data-stu-id="4efeb-111">Specify the number of folds.</span></span>  
  
-   <span data-ttu-id="4efeb-112">Geben Sie die maximale Anzahl von Fällen an, die für die übergreifende Überprüfung zu verwenden sind.</span><span class="sxs-lookup"><span data-stu-id="4efeb-112">Specify the maximum number of cases to use for cross-validation.</span></span>  
  
-   <span data-ttu-id="4efeb-113">Geben Sie die vorhersagbare Spalte an.</span><span class="sxs-lookup"><span data-stu-id="4efeb-113">Specify the predictable column.</span></span>  
  
-   <span data-ttu-id="4efeb-114">Geben Sie optional einen vorhersagbaren Status an.</span><span class="sxs-lookup"><span data-stu-id="4efeb-114">Optionally, specify a predictable state.</span></span>  
  
-   <span data-ttu-id="4efeb-115">Legen Sie optional Parameter fest, mit denen gesteuert wird, wie die Genauigkeit der Vorhersage bewertet wird.</span><span class="sxs-lookup"><span data-stu-id="4efeb-115">Optionally, set parameters that control how the accuracy of prediction is assessed.</span></span>  
  
-   <span data-ttu-id="4efeb-116">Klicken Sie auf **Ergebnisse abrufen** , um die Ergebnisse der übergreifenden Überprüfung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4efeb-116">Click **Get Results** to display the results of cross-validation.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="4efeb-117">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="4efeb-117">UI element list</span></span>  
 <span data-ttu-id="4efeb-118">**Foldanzahl**</span><span class="sxs-lookup"><span data-stu-id="4efeb-118">**Fold Count**</span></span>  
 <span data-ttu-id="4efeb-119">Geben Sie die Anzahl von zu erstellenden Aufteilungen (oder Partitionen) an.</span><span class="sxs-lookup"><span data-stu-id="4efeb-119">Specify the number of folds, or partitions, to create.</span></span> <span data-ttu-id="4efeb-120">Der Minimalwert ist 2. Das bedeutet, dass die eine Hälfte des Datasets zum Testen und die andere zum Trainieren verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4efeb-120">The minimum value is 2, meaning that half the data set is used for testing and half for training.</span></span>  
  
 <span data-ttu-id="4efeb-121">Der Maximalwert für Sitzungsminingstrukturen ist 10.</span><span class="sxs-lookup"><span data-stu-id="4efeb-121">The maximum value is 10 for session mining structures.</span></span>  
  
 <span data-ttu-id="4efeb-122">Der Maximalwert ist 256, wenn die Miningstruktur in einer Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="4efeb-122">The maximum value is 256 if the mining structure is stored in an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4efeb-123">Wenn Sie die Anzahl der Aufteilungen erhöhen, verlängert sich entsprechend auch die für die Ausführung der Kreuzvalidierung erforderliche Zeit um n.</span><span class="sxs-lookup"><span data-stu-id="4efeb-123">As you increase the number of folds, the time that is required to perform cross-validation similarly increases by n.</span></span> <span data-ttu-id="4efeb-124">Wenn der Wert von **Foldanzahl** zu hoch ist, können unter Umständen Leistungsprobleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="4efeb-124">You might experience performance issues if the number of cases is large and the value of **Fold Count** is also large.</span></span>  
  
 <span data-ttu-id="4efeb-125">**Maximale Anzahl von Fällen**</span><span class="sxs-lookup"><span data-stu-id="4efeb-125">**Max Cases**</span></span>  
 <span data-ttu-id="4efeb-126">Geben Sie die maximale Anzahl von Fällen an, die für die übergreifende Überprüfung zu verwenden sind.</span><span class="sxs-lookup"><span data-stu-id="4efeb-126">Specify the maximum number of cases to use for cross-validation.</span></span> <span data-ttu-id="4efeb-127">Die Anzahl von Fällen in einer bestimmten Aufteilung entspricht dem Wert **Maximale Anzahl von Fällen** geteilt durch den Wert **Foldanzahl** .</span><span class="sxs-lookup"><span data-stu-id="4efeb-127">The number of cases in any particular fold is equal to the **Max Cases** value divided by the **Fold Count** value.</span></span>  
  
 <span data-ttu-id="4efeb-128">Wenn Sie **0**verwenden, werden alle Fälle in den Quelldaten für die übergreifende Überprüfung verwendet.</span><span class="sxs-lookup"><span data-stu-id="4efeb-128">If you use **0**, all cases in the source data are used for cross-validation.</span></span>  
  
 <span data-ttu-id="4efeb-129">Es gibt keinen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="4efeb-129">There is no default value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4efeb-130">In dem Maße, in dem Sie die Anzahl von Fällen erhöhen, nimmt auch die Verarbeitungszeit zu.</span><span class="sxs-lookup"><span data-stu-id="4efeb-130">As you increase the number of cases, processing time also increases.</span></span>  
  
 <span data-ttu-id="4efeb-131">**Ziel Attribut**</span><span class="sxs-lookup"><span data-stu-id="4efeb-131">**Target Attribute**</span></span>  
 <span data-ttu-id="4efeb-132">Wählen Sie in der Liste der in allen Modellen vorhandenen vorhersagbaren Spalten eine Spalte aus.</span><span class="sxs-lookup"><span data-stu-id="4efeb-132">Select a column from the list of predictable columns found in all models.</span></span> <span data-ttu-id="4efeb-133">Sie können jeweils nur eine vorhersagbare Spalte auswählen, wenn Sie eine übergreifende Überprüfung ausführen.</span><span class="sxs-lookup"><span data-stu-id="4efeb-133">You can only select one predictable column every time that you perform cross-validation.</span></span>  
  
 <span data-ttu-id="4efeb-134">Wählen Sie **Cluster**aus, wenn Sie nur Clustermodelle testen möchten.</span><span class="sxs-lookup"><span data-stu-id="4efeb-134">To test only clustering models, select **Cluster**.</span></span>  
  
 <span data-ttu-id="4efeb-135">**Ziel Status**</span><span class="sxs-lookup"><span data-stu-id="4efeb-135">**Target State**</span></span>  
 <span data-ttu-id="4efeb-136">Geben Sie einen Wert ein, oder wählen Sie in einer Dropdownliste von Werten einen Zielwert aus.</span><span class="sxs-lookup"><span data-stu-id="4efeb-136">Type a value, or select a target value from a drop-down list of values.</span></span>  
  
 <span data-ttu-id="4efeb-137">Der Standardwert ist `null`. Dieser gibt an, dass alle Status zu testen sind.</span><span class="sxs-lookup"><span data-stu-id="4efeb-137">The default value is `null`, indicating that all states are to be tested.</span></span>  
  
 <span data-ttu-id="4efeb-138">Bei Clustermodellen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4efeb-138">Disabled for clustering models.</span></span>  
  
 <span data-ttu-id="4efeb-139">**Zielschwellenwert**  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4efeb-139">**Target**  **Threshold**</span></span>  
 <span data-ttu-id="4efeb-140">Geben Sie einen Wert zwischen 0 und 1 an, mit dem die Vorhersagewahrscheinlichkeit angegeben wird, oberhalb derer ein vorhergesagter Status als richtig gewertet wird.</span><span class="sxs-lookup"><span data-stu-id="4efeb-140">Specify a value between 0 and 1 that indicates the prediction probability above which a predicted state is considered to be correct.</span></span> <span data-ttu-id="4efeb-141">Der Wert kann in Schritten von 0,1 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4efeb-141">The value can be set in 0.1 increments.</span></span>  
  
 <span data-ttu-id="4efeb-142">Der Standardwert ist `null`. Dieser gibt an, dass die wahrscheinlichste Vorhersage als richtig gewertet wird.</span><span class="sxs-lookup"><span data-stu-id="4efeb-142">The default is `null`, indicating that the most probable prediction is counted as correct.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4efeb-143">Sie können den Wert zwar auf 0,0 festlegen, dadurch wird jedoch die Verarbeitungszeit erhöht, und es werden keine brauchbaren Ergebnisse geliefert.</span><span class="sxs-lookup"><span data-stu-id="4efeb-143">Although you can set the value to 0.0, using this value will increase processing time and not yield meaningful results.</span></span>  
  
 <span data-ttu-id="4efeb-144">**Ergebnisse abrufen**</span><span class="sxs-lookup"><span data-stu-id="4efeb-144">**Get Results**</span></span>  
 <span data-ttu-id="4efeb-145">Klicken Sie hierauf, um die übergreifende Überprüfung des Modells mit den angegebenen Parametern zu starten.</span><span class="sxs-lookup"><span data-stu-id="4efeb-145">Click to begin cross-validation of the model using the specified parameters.</span></span>  
  
 <span data-ttu-id="4efeb-146">Das Modell wird in die angegebene Anzahl von Aufteilungen partitioniert, und für jede Aufteilung wird ein separates Modell getestet.</span><span class="sxs-lookup"><span data-stu-id="4efeb-146">The model is partitioned into the specified number of folds and a separate model is tested for each fold.</span></span> <span data-ttu-id="4efeb-147">Deshalb kann es einige Zeit dauern, bis die übergreifende Überprüfung Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4efeb-147">Therefore, it might take some time for cross-validation to return the results.</span></span>  
  
 <span data-ttu-id="4efeb-148">Weitere Informationen zum Interpretieren der Ergebnisse des Berichts für die übergreifende Überprüfung finden Sie unter [Measures im Kreuzvalidierungsbericht](data-mining/measures-in-the-cross-validation-report.md).</span><span class="sxs-lookup"><span data-stu-id="4efeb-148">For more information about how to interpret the results of the cross-validation report, see [Measures in the Cross-Validation Report](data-mining/measures-in-the-cross-validation-report.md).</span></span>  
  
## <a name="setting-the-accuracy-threshold"></a><span data-ttu-id="4efeb-149">Festlegen des Genauigkeitsschwellenwerts</span><span class="sxs-lookup"><span data-stu-id="4efeb-149">Setting the Accuracy Threshold</span></span>  
 <span data-ttu-id="4efeb-150">Sie können den Standardwert zum Messen der Vorhersagegenauigkeit steuern, indem Sie einen Wert für **Ziel** **schwellenwert** festlegen.</span><span class="sxs-lookup"><span data-stu-id="4efeb-150">You can control the standard for measuring prediction accuracy by setting a value for **Target** **Threshold**.</span></span> <span data-ttu-id="4efeb-151">Ein Schwellenwert stellt eine Art von Genauigkeitsleiste dar.</span><span class="sxs-lookup"><span data-stu-id="4efeb-151">A threshold represents a kind of accuracy bar.</span></span> <span data-ttu-id="4efeb-152">Jeder Vorhersage wird eine Wahrscheinlichkeit der Richtigkeit des vorhergesagten Werts zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4efeb-152">Each prediction is assigned a probability that the predicted value is correct.</span></span> <span data-ttu-id="4efeb-153">Wenn Sie also den **Ziel** **schwellenwert** auf einen Wert festlegen, der näher an 1 liegt, muss die Wahrscheinlichkeit für eine bestimmte Vorhersage ziemlich hoch sein, damit diese als gute Vorhersage gewertet wird.</span><span class="sxs-lookup"><span data-stu-id="4efeb-153">Therefore, if you set the **Target** **Threshold** value closer to 1, you are requiring that the probability for any particular prediction to be fairly high to be counted as a good prediction.</span></span> <span data-ttu-id="4efeb-154">Wenn Sie umgekehrt den **Ziel** **schwellenwert** auf einen Wert festlegen, der näher an 0 liegt, werden auch Vorhersagen mit niedrigeren Wahrscheinlichkeitswerten als „gute“ Vorhersagen gewertet.</span><span class="sxs-lookup"><span data-stu-id="4efeb-154">Conversely, if you set **Target** **Threshold** closer to 0, even predictions with lower probability values are counted as "good" predictions.</span></span>  
  
 <span data-ttu-id="4efeb-155">Es gibt keinen empfohlenen Schwellenwert, da die Wahrscheinlichkeit einer Vorhersage von der Datenmenge und dem Typ der Vorhersage abhängt.</span><span class="sxs-lookup"><span data-stu-id="4efeb-155">There is no recommended threshold value because the probability of any prediction depends on the amount of data and the type of prediction you are making.</span></span> <span data-ttu-id="4efeb-156">Prüfen Sie einige Vorhersagen auf verschiedenen Wahrscheinlichkeitsstufen, um eine geeignete Genauigkeitsleiste für Ihre Daten zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="4efeb-156">You should review some predictions at different probability levels to determine an appropriate accuracy bar for your data.</span></span> <span data-ttu-id="4efeb-157">Diese Vorgehensweise ist von Bedeutung, da der Wert, den Sie für **Ziel** **schwellenwert** verwenden, Auswirkungen auf die gemessene Genauigkeit des Modells hat.</span><span class="sxs-lookup"><span data-stu-id="4efeb-157">It is important that you do this, because the value that you set for **Target** **Threshold** affects the measured accuracy of the model.</span></span>  
  
 <span data-ttu-id="4efeb-158">Angenommen, es werden drei Vorhersagen für einen bestimmten Zielstatus erstellt, und die Wahrscheinlichkeiten für die einzelnen Vorhersagen liegen bei 0,05, 0,15 und 0,8.</span><span class="sxs-lookup"><span data-stu-id="4efeb-158">For example, suppose three predictions are made for a particular target state, and the probabilities of each prediction are 0.05, 0.15, and 0.8.</span></span> <span data-ttu-id="4efeb-159">Wenn Sie den Schwellenwert auf 0,5 festgelegt haben, wird nur eine Vorhersage als richtig gewertet.</span><span class="sxs-lookup"><span data-stu-id="4efeb-159">If you set the threshold to 0.5, only one prediction is counted as being correct.</span></span> <span data-ttu-id="4efeb-160">Wenn Sie den **Ziel** **schwellenwert** auf 0,10 festgelegt haben, werden zwei der Vorhersagen als richtig gewertet.</span><span class="sxs-lookup"><span data-stu-id="4efeb-160">If you set **Target** **Threshold** to 0.10, two predictions are counted as being correct.</span></span>  
  
 <span data-ttu-id="4efeb-161">Wenn der **Ziel** **Schwellen** Wert auf festgelegt ist ( `null` Dies ist der Standardwert), wird die wahrscheinlichste Vorhersage für jeden Fall als richtig gezählt.</span><span class="sxs-lookup"><span data-stu-id="4efeb-161">When **Target** **Threshold** is set to `null`, which is the default value, the most probable prediction for each case is counted as correct.</span></span> <span data-ttu-id="4efeb-162">In dem gerade genannten Beispiel sind 0,05, 0,15 und 0,8 die Wahrscheinlichkeiten für Vorhersagen in drei verschiedenen Fällen.</span><span class="sxs-lookup"><span data-stu-id="4efeb-162">In the example just cited, 0.05, 0.15, and 0.8 are the probabilities for predictions in three different cases.</span></span> <span data-ttu-id="4efeb-163">Obwohl die Wahrscheinlichkeiten sehr unterschiedlich sind, würde jede Vorhersage als richtig gewertet, da jeder Fall nur eine Vorhersage generiert und es sich dabei um die besten Vorhersagen für diese Fälle handelt.</span><span class="sxs-lookup"><span data-stu-id="4efeb-163">Although the probabilities are very different, each prediction would be counted as correct, because each case generates only one prediction and these are the best predictions for these cases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4efeb-164">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4efeb-164">See Also</span></span>  
 <span data-ttu-id="4efeb-165">[Testen und validieren &#40;Data Mining-&#41;](data-mining/testing-and-validation-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="4efeb-165">[Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md) </span></span>  
 <span data-ttu-id="4efeb-166">[Übergreifende Überprüfung &#40;Analysis Services Data Mining-&#41;](data-mining/cross-validation-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="4efeb-166">[Cross-Validation &#40;Analysis Services - Data Mining&#41;](data-mining/cross-validation-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="4efeb-167">[Measures im Kreuz Validierungsbericht](data-mining/measures-in-the-cross-validation-report.md) </span><span class="sxs-lookup"><span data-stu-id="4efeb-167">[Measures in the Cross-Validation Report](data-mining/measures-in-the-cross-validation-report.md) </span></span>  
 [<span data-ttu-id="4efeb-168">Data Mining-gespeicherte Prozeduren &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="4efeb-168">Data Mining Stored Procedures &#40;Analysis Services - Data Mining&#41;</span></span>](/sql/analysis-services/data-mining/data-mining-stored-procedures-analysis-services-data-mining)  
  
  