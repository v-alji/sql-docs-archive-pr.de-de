---
title: Durchsuchen eines neuronalen Netzwerk Modells | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining models, browsing
- mining models, viewing
- mining model, neural network
- neural networks
- dependency network
ms.assetid: e4224cb7-115b-4889-ac07-03f096fb55fc
author: minewiskan
ms.author: owend
ms.openlocfilehash: ab2673d5b1881f74c2bc146b084d2efc7b06d69b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610307"
---
# <a name="browsing-a-neural-network-model"></a><span data-ttu-id="2f7d8-102">Durchsuchen von Neural Network-Modellen</span><span class="sxs-lookup"><span data-stu-id="2f7d8-102">Browsing a Neural Network Model</span></span>
  <span data-ttu-id="2f7d8-103">Wenn Sie ein neuronales Netzwerk oder ein logistisches Regressionsmodell mithilfe von **Durchsuchen** öffnen, wird das Modell in einem interaktiven Viewer angezeigt, der mit dem Viewer für neuronale Netzwerkmodelle in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] vergleichbar ist.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-103">When you open a neural network or logistic regression model using **Browse**, the model is displayed in an interactive viewer, similar to the neural network model viewer in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="2f7d8-104">Mithilfe des Viewers können Sie Korrelationen untersuchen und Informationen zu den Mustern im Modell und zu den zugrunde liegenden Daten abrufen.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-104">The viewer helps you explore correlations, and get information about the patterns in the model and the underlying data.</span></span>

##  <a name="explore-the-model"></a><a name="BKMK_Tabs"></a><span data-ttu-id="2f7d8-105">Untersuchen des Modells</span><span class="sxs-lookup"><span data-stu-id="2f7d8-105">Explore the Model</span></span>
 <span data-ttu-id="2f7d8-106">Modelle, die auf den [!INCLUDE[msCoName](../includes/msconame-md.md)]-Algorithmen "Neural Network" oder "Logistic Regression" basieren, ähneln sich insofern, als sie Daten als eine Gruppe von Verbindungen zwischen bekannten Eingaben und Ausgaben analysieren.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-106">Models that are based on [!INCLUDE[msCoName](../includes/msconame-md.md)] Neural Network or Logistic Regression algorithms are similar in that they analyze data as a set of connections among known inputs and outputs.</span></span> <span data-ttu-id="2f7d8-107">Mit dem **Durchsuchen**-Viewer können Sie diese Verbindungen mithilfe der folgenden Steuerelemente untersuchen:</span><span class="sxs-lookup"><span data-stu-id="2f7d8-107">The **Browse** viewer helps you to explore those connections, using the following controls:</span></span>

-   [<span data-ttu-id="2f7d8-108">Variablen</span><span class="sxs-lookup"><span data-stu-id="2f7d8-108">Variables</span></span>](#BKMK_Variables)

-   [<span data-ttu-id="2f7d8-109">Eingaben</span><span class="sxs-lookup"><span data-stu-id="2f7d8-109">Inputs</span></span>](#BKMK_Inputs)

-   [<span data-ttu-id="2f7d8-110">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="2f7d8-110">Outputs</span></span>](#BKMK_Outputs)

 <span data-ttu-id="2f7d8-111">Zum Testen dieses Viewers können Sie ein Modell mit dem [Assistent zum Klassifizieren &#40;Data Mining-Add-Ins für Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) erstellen und die Option **Erweitert** verwenden, um den Algorithmus im Dialogfeld **Algorithmusparameter** in Microsoft Logistic Regression zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-111">If you want to experiment with this viewer, you can create a model using the [Classify Wizard &#40;Data Mining Add-ins for Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) wizard, and use the **Advanced** option to change the algorithm to Microsoft Logistic Regression in the **Algorithm Parameters** dialog box.</span></span>

###  <a name="variables"></a><a name="BKMK_Variables"></a><span data-ttu-id="2f7d8-112">Instan</span><span class="sxs-lookup"><span data-stu-id="2f7d8-112">Variables</span></span>
 <span data-ttu-id="2f7d8-113">Im Bereich **Variablen** wird eine Liste der Eingabevariablen in der Reihenfolge angezeigt, in der sie sich auf das Modell auswirken.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-113">The **Variables** pane displays a list of input variables in order of their effect on the model.</span></span> <span data-ttu-id="2f7d8-114">Sie verwenden die Steuerelemente **Eingabe** und **Ausgabe**, um das Modell zu filtern. Dadurch können Sie beeinflussen, welche Variablen angezeigt und in welcher Reihenfolge sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-114">You use the **Input** and **Output** controls to filter the model, affecting the variables that are displayed, as well as their order.</span></span>

 <span data-ttu-id="2f7d8-115">Mit diesem Viewer können Sie die Faktoren untersuchen, die den größten Einfluss darauf haben, ob ein Kunde eher der Fahrradkäuferkategorie oder der Nichtkäuferkategorie angehört.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-115">Using this viewer, you can explore the factors that are most important in determining whether a customer more likely belongs to the bike buyer category or the non-buyer category.</span></span>

 <span data-ttu-id="2f7d8-116">![Testen der Auswirkung ausgewählter Attribute auf das Ergebnis](media/dm13-neuralnet-agebuyer1.gif "Testen der Auswirkung ausgewählter Attribute auf das Ergebnis")</span><span class="sxs-lookup"><span data-stu-id="2f7d8-116">![Testing effect on outcome of selected attributes](media/dm13-neuralnet-agebuyer1.gif "Testing effect on outcome of selected attributes")</span></span>

##### <a name="explore-variables"></a><span data-ttu-id="2f7d8-117">Untersuchen von Variablen</span><span class="sxs-lookup"><span data-stu-id="2f7d8-117">Explore variables</span></span>

1.  <span data-ttu-id="2f7d8-118">Zunächst wird der Bereich **Variablen** auf der Grundlage der aktuellen Filter nach den wichtigsten Attributen sortiert.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-118">Initially, the **Variables** pane is sorted in order of the most important attributes, given the current filters.</span></span> <span data-ttu-id="2f7d8-119">Die Länge des Balkens gibt die Stärke des Faktors an.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-119">The length of the bar indicates the strength of the factor.</span></span>

     <span data-ttu-id="2f7d8-120">Im Beispiel können Sie erkennen, dass das Einkommen, gefolgt von der Region, der größte Einflussfaktor ist.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-120">In the example, you can see that income is the most influential factor, followed by region.</span></span> <span data-ttu-id="2f7d8-121">Andererseits werden kinderreiche Familien, die mehrere Autos besitzen, aller Wahrscheinlichkeit nach kein Fahrrad kaufen.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-121">On the other hand, customers with many cars and many children are highly unlikely to buy a bike.</span></span>

2.  <span data-ttu-id="2f7d8-122">Klicken Sie im Bereich **Variablen** auf die Spaltenüberschrift für **Attribut**.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-122">In the **Variables** pane, click the column heading for **Attribute**.</span></span>

     <span data-ttu-id="2f7d8-123">Beim Sortieren nach Attributen sehen Sie die Container, die für die einzelnen Eingabespalten erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-123">By sorting on attribute, you can see the bins that were created for each of the input columns.</span></span> <span data-ttu-id="2f7d8-124">Spalten mit diskreten Werten, z. B. Beruf, werden nach den *Literalwerten* klassifiziert.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-124">Columns with discrete values, such as occupation, are *binned* by the literal values.</span></span>

3.  <span data-ttu-id="2f7d8-125">Beachten Sie die Wertebereiche, die für **Alter** und **Einkommen** gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-125">Notice the ranges of values that were found for **Age** and **Income**.</span></span>

     <span data-ttu-id="2f7d8-126">Wenn eine der Eingabespalten aus Zahlen besteht (d. h., die ganze Datenspalte weist einen Datentyp mit fortlaufenden numerischen Zahlen auf), werden die Zahlen Buckets zugeordnet oder in diskreten Bereichen klassifiziert.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-126">If any of your input columns are numbers (that is, the entire column of data is a continuous numeric data type), the numbers are bucketed, or binned, into discrete ranges.</span></span>

     <span data-ttu-id="2f7d8-127">Die Einkommensspalte wurde in Gruppierungen wie 78,4-154,06 (höchste Einkommensstufe) unterteilt.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-127">For Income, the column has been subdivided into groupings such as 78.4-154.06 (for the uppermost income range).</span></span>

     <span data-ttu-id="2f7d8-128">![Sortieren, um zu ermitteln, wie Variablen klassifiziert wurden](media/dm13-nn-bucketing-variables.gif "Sortieren, um zu ermitteln, wie Variablen klassifiziert wurden")</span><span class="sxs-lookup"><span data-stu-id="2f7d8-128">![sort to view how variables were binned](media/dm13-nn-bucketing-variables.gif "sort to view how variables were binned")</span></span>

     <span data-ttu-id="2f7d8-129">Wenn Sie unterschiedliche Gruppierungen verwenden möchten, sollten Sie das Tool [Neu bezeichnen &#40;SQL Server Data Mining Add-Ins&#41;](relabel-sql-server-data-mining-add-ins.md) oder die Excel-Funktionen verwenden, um vor der Modellerstellung neue Einkommenskategorien einzurichten.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-129">If you want different groupings, you should use the [Relabel &#40;SQL Server Data Mining Add-ins&#41;](relabel-sql-server-data-mining-add-ins.md) tool, or Excel functions, to create new income categories before building the model.</span></span>

4.  <span data-ttu-id="2f7d8-130">Klicken Sie auf **Begünstigt Ja**, um das Diagramm in der Standardansicht wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-130">Click **Favors Yes** to restore the graph to the default view.</span></span>

     <span data-ttu-id="2f7d8-131">Standardmäßig wird die Ansicht nach dem Wert von **Begünstigt** sortiert, der als erster Ergebniswert festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-131">By default, the view is sorted by the value of **Favors** for the first outcome value.</span></span> <span data-ttu-id="2f7d8-132">Sie können ändern, welche Ergebnisse der ersten und zweiten Spalte zugeordnet werden, indem Sie in **Ausgabe** einen neuen Wert für **Wert 1** und **Wert 2** auswählen.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-132">You can change which outcomes are assigned to the first and second columns by choosing a new value for **Value 1** and **Value 2** in **Output**.</span></span>

5.  <span data-ttu-id="2f7d8-133">Positionieren Sie die Maus auf dem obersten Farbbalken im Diagramm.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-133">Pause the mouse over the topmost colored bar in the chart.</span></span>

     <span data-ttu-id="2f7d8-134">Eine QuickInfo wird angezeigt, die ein Ergebnis für *Wichtigkeit*, ein Ergebnispaar für *Wahrscheinlichkeit* und ein Ergebnispaar für *Prognosegüte* enthält.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-134">A ToolTip appears that includes an *importance* score, a pair of *probability* scores, and a pair of *lift* values.</span></span>

    -   <span data-ttu-id="2f7d8-135">Die **Wichtigkeit** wird für das gesamte Dataset berechnet. Sie identifiziert das Attribut, das auf der Grundlage aller Eingaben die stärkste Korrelation mit dem Zielergebnis aufweist.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-135">**Importance** is calculated across the entire dataset, and identifies the attribute that, given all inputs, is most correlated with the target outcome.</span></span> <span data-ttu-id="2f7d8-136">Der Viewer sortiert die Werte im Diagramm nach den Wichtigkeitsbewertungen.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-136">The viewer sorts the values in the chart by the importance scores.</span></span>

    -   <span data-ttu-id="2f7d8-137">Die **Wahrscheinlichkeit** wird für die einzelnen Sätze von Attribut/Wert-Paaren im gesamten Dataset berechnet und in den Zielergebnissen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-137">**Probability** is calculated for each set of attribute-value pairs, for the target outcomes, across the entire data set.</span></span>

    -   <span data-ttu-id="2f7d8-138">Die **Prognosegüte** gibt an, wie hilfreich ein bestimmtes Attribut/Wert-Paar für die Höherstufung eines Ergebnisses ist.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-138">**Lift** tells you how useful this particular attribute-value pair is for promoting one outcome or another.</span></span>

     <span data-ttu-id="2f7d8-139">Hinweis: Die QuickInfo enthält die gleichen Informationen, unabhängig davon, ob Sie die Maus auf der einen oder anderen Spalte positionieren.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-139">Note: The ToolTip contains the same information no matter whether you position the mouse over one column or the other.</span></span>

 [<span data-ttu-id="2f7d8-140">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="2f7d8-140">Back To Top</span></span>](#BKMK_Tabs)

###  <a name="inputs"></a><a name="BKMK_Inputs"></a><span data-ttu-id="2f7d8-141">Ungs</span><span class="sxs-lookup"><span data-stu-id="2f7d8-141">Inputs</span></span>
 <span data-ttu-id="2f7d8-142">Im Bereich **Eingaben** können Sie einen Satz von Eingaben auswählen und diesen als Filter auf das Modell anwenden. So erkennen Sie auf der Grundlage der Trainingsdaten, wie sich diese Optionen auf das Ergebnis auswirken.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-142">The **Inputs** pane lets you choose a set of inputs and apply that as a filter to the model, which lets you see the influence of those choices on the outcome, based on the training data</span></span>

##### <a name="explore-inputs"></a><span data-ttu-id="2f7d8-143">Untersuchen von Eingaben</span><span class="sxs-lookup"><span data-stu-id="2f7d8-143">Explore inputs</span></span>

1.  <span data-ttu-id="2f7d8-144">Stellen Sie sich vor, Sie möchten eine bestimmte Zielgruppe analysieren und die Faktoren anzeigen, die den größten Einfluss auf das Kaufverhalten der Gruppe haben.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-144">Suppose you want to target a particular group, and see the factors that most influence purchasing in that group.</span></span>

     <span data-ttu-id="2f7d8-145">Klicken Sie im Bereich **Eingabe** **\<All>** unter **Attribut**auf die Zelle, und wählen Sie **Alter**aus.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-145">In the **Input** pane, click the **\<All>** cell under **Attribute**, and select **Age**.</span></span>

     <span data-ttu-id="2f7d8-146">Wählen Sie für **Wert** die jüngste Altersgruppe aus.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-146">For **Value**, select the youngest age category.</span></span>

2.  <span data-ttu-id="2f7d8-147">Auch wenn Sie nach einer bestimmten Altersgruppe filtern, werden Sie feststellen, dass die Pazifikregion fast am Anfang der Liste steht.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-147">Notice that even when you filter on a particular age group, the Pacific region comes to near the top of the list.</span></span> <span data-ttu-id="2f7d8-148">Das liegt daran, dass Kunden aus der Pazifikregion mit weitaus größerer Wahrscheinlichkeit ein Fahrrad kaufen würden als Kunden in anderen Regionen.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-148">This is because customers in the Pacific region are far more likely to buy a bike than customers in other regions.</span></span>

     <span data-ttu-id="2f7d8-149">Da die Region eine Größe ist, die Sie nicht beeinflussen können, können Sie die Eingaben ändern, um diese Variable aus der Analyse zu entfernen und andere Faktoren zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-149">Since region is not something you can influence, to remove this variable from consideration and see other factors, you can change the inputs again.</span></span>

     <span data-ttu-id="2f7d8-150">Klicken Sie im Bereich **Eingabe** auf die leere Zelle unter **Alter**, und wählen Sie **Region** aus.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-150">In the **Input** pane, click the empty cell under **Age**, and select **Region**.</span></span>

     <span data-ttu-id="2f7d8-151">Wählen Sie für **Wert** den Eintrag **Europa** aus.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-151">For **Value**, select **Europe**.</span></span>

3.  <span data-ttu-id="2f7d8-152">Fügen Sie weitere Eingabefilter hinzu, um eine bestimmte Interessensgruppe zu fokussieren.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-152">Continue adding input filters to focus on a group of particular interest.</span></span>

     <span data-ttu-id="2f7d8-153">Fügen Sie für das Eingabeattribut beispielsweise **Geschlecht** hinzu, und wählen Sie **Weiblich** als Wert aus.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-153">For example, for the input attribute, add **Gender**, and select **Female** as the value.</span></span>

     <span data-ttu-id="2f7d8-154">![Testen der Auswirkung ausgewählter Attribute auf das Ergebnis](media/dm13-neuralnet-agebuyer2.gif "Testen der Auswirkung ausgewählter Attribute auf das Ergebnis")</span><span class="sxs-lookup"><span data-stu-id="2f7d8-154">![Testing effect on outcome of selected attributes](media/dm13-neuralnet-agebuyer2.gif "Testing effect on outcome of selected attributes")</span></span>

     <span data-ttu-id="2f7d8-155">Sie werden feststellen, dass sich die Liste der Variablen ändert.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-155">Notice how the list of variables changes.</span></span> <span data-ttu-id="2f7d8-156">Jetzt ist **Einkommen** die Variable, die für die Vorhersage des Zielergebnisses die größte Bedeutung hat.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-156">Now **Income** is the variable that is most important in predicting the target outcome.</span></span>

     <span data-ttu-id="2f7d8-157">Die Reihenfolge, in der Sie die Eingabefilter anwenden, wirkt sich nicht auf die Ergebnisse aus.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-157">The order in which you apply the input filters does not affect the results.</span></span>

 [<span data-ttu-id="2f7d8-158">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="2f7d8-158">Back To Top</span></span>](#BKMK_Tabs)

###  <a name="outputs"></a><a name="BKMK_Outputs"></a><span data-ttu-id="2f7d8-159">Ausgaben</span><span class="sxs-lookup"><span data-stu-id="2f7d8-159">Outputs</span></span>
 <span data-ttu-id="2f7d8-160">Im Bereich **Ausgabe** können Sie das Ergebnis auswählen, das interessant für Sie ist.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-160">In the **Outputs** pane, you can choose the outcome that you are interested in.</span></span> <span data-ttu-id="2f7d8-161">In neuronalen Netzwerken können Sie so viele Ergebnisspalten angeben, wie Sie möchten. Allerdings erhöht sich durch zusätzliche Ausgaben auch die Komplexität des Modells, sodass sich die Verarbeitungsdauer verlängern kann.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-161">Neural networks let you specify as many outcome columns as you like, although adding more outputs adds to the complexity of the model and may require a much longer time to process.</span></span>

 <span data-ttu-id="2f7d8-162">Um zwei Ausgaben zu vergleichen, müssen die Spalten den Typ **Vorhersagen** oder **Nur vorhersagen** aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-162">To compare two outputs, they must have been designated as **Predict** or **Predict Only** columns.</span></span>

##### <a name="explore-outputs"></a><span data-ttu-id="2f7d8-163">Untersuchen von Ausgaben</span><span class="sxs-lookup"><span data-stu-id="2f7d8-163">Explore outputs</span></span>

1.  <span data-ttu-id="2f7d8-164">Verwenden Sie die Liste **Ausgabeattribut**, um ein Attribut auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-164">Use the **Output Attribute** list to select an attribute.</span></span>

2.  <span data-ttu-id="2f7d8-165">Wählen Sie zwei Ergebnisse aus den Listen Wert 1 und Wert 2 aus.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-165">Select two outcomes from the Value 1 and Value 2 lists.</span></span> <span data-ttu-id="2f7d8-166">Diese beiden Status der Ausgabeattribute werden im Bereich **Variablen** verglichen.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-166">These two states of the output attribute will be compared in the **Variables** pane.</span></span>

 [<span data-ttu-id="2f7d8-167">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="2f7d8-167">Back To Top</span></span>](#BKMK_Tabs)

## <a name="more-about-neural-network-models"></a><span data-ttu-id="2f7d8-168">Weiteren Informationen über neuronale Netzwerkmodelle</span><span class="sxs-lookup"><span data-stu-id="2f7d8-168">More About Neural Network Models</span></span>
 <span data-ttu-id="2f7d8-169">Die im Viewer dargestellten Informationen werden anhand einer gespeicherten Prozedur, die spezifisch für den Modelltyp ist, vom Server abgerufen: System.Microsoft.AnalysisServices.System.DataMining.NeuralNet.GetAttributeScores.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-169">The information in the viewer is retrieved from the server using a stored procedure specific to this model type: System.Microsoft.AnalysisServices.System.DataMining.NeuralNet.GetAttributeScores.</span></span>

 <span data-ttu-id="2f7d8-170">Wenn Sie ein Modell mit mehreren vorhersagbaren Attributen mithilfe der Add-Ins erstellen möchten, verwenden Sie die Modellierungsoptionen unter **Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="2f7d8-170">If you want to create a model with multiple predictable attributes using the add-ins, use the **Advanced** modeling options.</span></span>

 <span data-ttu-id="2f7d8-171">Weitere Informationen finden Sie unter [Erstellen einer Miningstruktur &#40;SQL Server Data Mining-Add-Ins&#41;](create-mining-structure-sql-server-data-mining-add-ins.md) und [Hinzufügen eines Modells zu einer Struktur &#40;Data Mining-Add-Ins für Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="2f7d8-171">For more information, see [Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;](create-mining-structure-sql-server-data-mining-add-ins.md) and [Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2f7d8-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f7d8-172">See Also</span></span>
 [<span data-ttu-id="2f7d8-173">Durchsuchen von Modellen in Excel &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="2f7d8-173">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)


