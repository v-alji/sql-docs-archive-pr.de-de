---
title: Testen eines gefilterten Modells (Lernprogramm zu Data Mining-Grundlagen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f0d74f8c-600d-4df5-a742-695e6947a071
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a97b5ca3523d1fc73405baba52b179a9bef04767
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608130"
---
# <a name="testing-a-filtered-model-basic-data-mining-tutorial"></a><span data-ttu-id="a257d-102">Testen eines gefilterten Modells (Lernprogramm zu Data Mining-Grundlagen)</span><span class="sxs-lookup"><span data-stu-id="a257d-102">Testing a Filtered Model (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="a257d-103">Nachdem Sie festgestellt haben, dass das `TM_Decision_Tree` Modell am genauesten ist, passen Sie das Modell so an, dass es den Anforderungen der [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] Ziel-Mailingkampagne besser entspricht.</span><span class="sxs-lookup"><span data-stu-id="a257d-103">Now that you have determined that the `TM_Decision_Tree` model is the most accurate, you will customize the model to better suit the needs of the [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] targeted mailing campaign.</span></span> <span data-ttu-id="a257d-104">Die Marketingabteilung möchte insbesondere ermitteln, ob Unterschiede zwischen männlichen und weiblichen Kunden vorliegen.</span><span class="sxs-lookup"><span data-stu-id="a257d-104">Specifically, the Marketing department would like to know if there are any differences between male and female customers.</span></span> <span data-ttu-id="a257d-105">Anhand dieser Informationen soll entschieden werden, welche Zeitschriften für Werbemaßnahmen berücksichtigt und welche Produkte beworben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a257d-105">The information could help them decide which magazines to use for advertising and which products to feature in their mailings.</span></span>  
  
## <a name="using-filters"></a><span data-ttu-id="a257d-106">Verwenden von Filtern</span><span class="sxs-lookup"><span data-stu-id="a257d-106">Using Filters</span></span>  
 <span data-ttu-id="a257d-107">Filter ermöglichen es Ihnen, auf einfache Weise Modelle für Teilmengen von Daten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a257d-107">Filtering enables you to easily create models built on subsets of your data.</span></span> <span data-ttu-id="a257d-108">Der Filter wird nur auf das Modell angewendet; die zugrunde liegende Datenquelle wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="a257d-108">The filter is applied only to the model and does not change the underlying data source.</span></span>  
  
 <span data-ttu-id="a257d-109">In dieser Lektion erstellen Sie ein nach Geschlechtern gefiltertes Modell, um die Merkmale mit dem stärksten Einfluss auf das Kaufverhalten männlicher und weiblicher Kunden vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="a257d-109">In this lesson, you will create a model that is filtered on gender, to predict the characteristics that most influence buying behavior in males and female.</span></span>  
  
 <span data-ttu-id="a257d-110">Zuerst erstellen Sie eine Kopie des `TM_Decision_Tree` Modells.</span><span class="sxs-lookup"><span data-stu-id="a257d-110">First you will make a copy of the `TM_Decision_Tree` model.</span></span>  
  
#### <a name="to-copy-the-decision-tree-model"></a><span data-ttu-id="a257d-111">So kopieren Sie das Entscheidungsstrukturmodell</span><span class="sxs-lookup"><span data-stu-id="a257d-111">To copy the Decision Tree Model</span></span>  
  
1.  <span data-ttu-id="a257d-112">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]Wählen Sie in Projektmappen-Explorer die Option **basicdatamining**aus.</span><span class="sxs-lookup"><span data-stu-id="a257d-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in Solution Explorer, select **BasicDataMining**.</span></span>  
  
2.  <span data-ttu-id="a257d-113">Klicken Sie auf die Registerkarte **Miningmodelle** .</span><span class="sxs-lookup"><span data-stu-id="a257d-113">Click the **Mining Models** tab.</span></span>  
  
3.  <span data-ttu-id="a257d-114">Klicken Sie mit der rechten Maustaste auf das `TM_Decision_Tree` Modell, und wählen Sie **Neues Mining Modell**</span><span class="sxs-lookup"><span data-stu-id="a257d-114">Right click the `TM_Decision_Tree` model, and select **New Mining Model.**</span></span>  
  
4.  <span data-ttu-id="a257d-115">Geben Sie im Feld **Modellname den Namen** ein `TM_Decision_Tree_Male` .</span><span class="sxs-lookup"><span data-stu-id="a257d-115">In the **Model name** field, type `TM_Decision_Tree_Male`.</span></span>  
  
5.  <span data-ttu-id="a257d-116">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a257d-116">Click **OK**.</span></span>  
  
 <span data-ttu-id="a257d-117">Erstellen Sie anschließend einen Filter, um Kunden auf Grundlage ihres Geschlechtes für das Modell auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="a257d-117">Next, create a filter to select customers for the model based on their gender.</span></span>  
  
#### <a name="to-create-a-case-filter-on-a-mining-model"></a><span data-ttu-id="a257d-118">So erstellen Sie einen Fallfilter für ein Miningmodell</span><span class="sxs-lookup"><span data-stu-id="a257d-118">To create a case filter on a mining model</span></span>  
  
1.  <span data-ttu-id="a257d-119">Klicken Sie mit der rechten Maustaste `TM_Decision_Tree_Male` auf das Mining Modell, um das Kontextmenü zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a257d-119">Right-click the `TM_Decision_Tree_Male` mining model to open the shortcut menu.</span></span>  
  
     <span data-ttu-id="a257d-120">– oder –</span><span class="sxs-lookup"><span data-stu-id="a257d-120">-- or --</span></span>  
  
     <span data-ttu-id="a257d-121">Wählen Sie das Modell aus.</span><span class="sxs-lookup"><span data-stu-id="a257d-121">Select the model.</span></span> <span data-ttu-id="a257d-122">Wählen Sie im Menü **Miningmodell** die Option **Modellfilter festlegen**aus.</span><span class="sxs-lookup"><span data-stu-id="a257d-122">On the **Mining Model** menu, select **Set Model Filter**.</span></span>  
  
2.  <span data-ttu-id="a257d-123">Klicken Sie im Dialogfeld **Modellfilter** im Textfeld **Miningstrukturspalte** auf die oberste Zeile im Raster.</span><span class="sxs-lookup"><span data-stu-id="a257d-123">In the **Model Filter** dialog box, click the top row in the grid, in the **Mining Structure Column** text box.</span></span>  
  
     <span data-ttu-id="a257d-124">Die Dropdownliste zeigt nur die Namen der Spalten in dieser Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="a257d-124">The drop-down list displays only the names of the columns in that table.</span></span>  
  
3.  <span data-ttu-id="a257d-125">Wählen Sie im Textfeld Mining Struktur Spalte die Option **Geschlecht**aus.</span><span class="sxs-lookup"><span data-stu-id="a257d-125">In the Mining Structure Column text box, select **Gender**.</span></span>  
  
     <span data-ttu-id="a257d-126">Das Symbol auf der linken Seite des Textfelds ändert sich und gibt dadurch an, dass es sich beim ausgewählten Element um eine Tabelle oder eine Spalte handelt.</span><span class="sxs-lookup"><span data-stu-id="a257d-126">The icon at the left side of the text box changes to indicate that the selected item is a table or a column.</span></span>  
  
4.  <span data-ttu-id="a257d-127">Klicken Sie auf das Textfeld **Operator** , und wählen Sie den Gleichheits Operator (=) aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="a257d-127">Click the **Operator** text box and select the equal (=) operator from the list.</span></span>  
  
5.  <span data-ttu-id="a257d-128">Klicken Sie auf das Textfeld **Wert** , und geben Sie **M**ein.</span><span class="sxs-lookup"><span data-stu-id="a257d-128">Click the **Value** text box, and type **M**.</span></span>  
  
6.  <span data-ttu-id="a257d-129">Klicken Sie auf die nächste Zeile im Raster.</span><span class="sxs-lookup"><span data-stu-id="a257d-129">Click the next row in the grid.</span></span>  
  
7.  <span data-ttu-id="a257d-130">Klicken Sie auf **OK** , um das Dialogfeld **Modell Filter** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="a257d-130">Click **OK** to close the **Model Filter** dialog box.</span></span>  
  
     <span data-ttu-id="a257d-131">Der Filter wird im Fenster **Eigenschaften** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a257d-131">The filter displays in the **Properties** window.</span></span> <span data-ttu-id="a257d-132">Alternativ können Sie das Dialogfeld **Modell Filter** im Fenster **Eigenschaften** starten.</span><span class="sxs-lookup"><span data-stu-id="a257d-132">Alternately, you can launch the **Model Filter** dialog from the **Properties** window.</span></span>  
  
8.  <span data-ttu-id="a257d-133">Wiederholen Sie die obigen Schritte, benennen Sie das Modell mit dieser Zeit, `TM_Decision_Tree_Female` und geben Sie **F** im Textfeld **Wert** ein.</span><span class="sxs-lookup"><span data-stu-id="a257d-133">Repeat the above steps, but this time name the model `TM_Decision_Tree_Female` and type **F** in the **Value** text box.</span></span>  
  
## <a name="process-the-filtered-models"></a><span data-ttu-id="a257d-134">Verarbeiten der gefilterten Modelle</span><span class="sxs-lookup"><span data-stu-id="a257d-134">Process the Filtered Models</span></span>  
 <span data-ttu-id="a257d-135">Modelle können erst dann verwendet werden, wenn sie bereitgestellt und verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="a257d-135">Models cannot be used until they have been deployed and processed.</span></span> <span data-ttu-id="a257d-136">Weitere Informationen zur Verarbeitung von Modellen finden Sie unter [Verarbeiten von Modellen in der Ziel-e-Mail-&#40;grundlegende Data Mining ](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md)-Lernprogramm&#41;.</span><span class="sxs-lookup"><span data-stu-id="a257d-136">For more information on processing models, see [Processing Models in the Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;](../../2014/tutorials/processing-models-in-the-targeted-mailing-structure-basic-data-mining-tutorial.md).</span></span>  
  
#### <a name="to-process-the-filtered-model"></a><span data-ttu-id="a257d-137">So verarbeiten Sie das gefilterte Modell</span><span class="sxs-lookup"><span data-stu-id="a257d-137">To process the filtered model</span></span>  
  
1.  <span data-ttu-id="a257d-138">Klicken Sie mit der rechten Maustaste auf das `TM_Decision_Tree_Male` Modell, und wählen Sie **Mining Struktur und alle Modelle verarbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a257d-138">Right-click the `TM_Decision_Tree_Male` model and select **Process Mining Structure and all Model**s</span></span>  
  
2.  <span data-ttu-id="a257d-139">Klicken Sie auf **Ausführen** , um die neuen Modelle zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a257d-139">Click **Run** to process the new models.</span></span>  
  
3.  <span data-ttu-id="a257d-140">Nachdem die Verarbeitung abgeschlossen ist, klicken Sie in beiden Verarbeitungs Fenstern auf **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="a257d-140">After processing is complete, click **Close** on both processing windows.</span></span>  
  
     <span data-ttu-id="a257d-141">Auf der Registerkarte **Mining Modelle** werden nun zwei neue Modelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a257d-141">You now have two new models displayed in the **Mining Models** tab.</span></span>  
  
## <a name="evaluate-the-results"></a><span data-ttu-id="a257d-142">Auswerten der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="a257d-142">Evaluate the Results</span></span>  
 <span data-ttu-id="a257d-143">Zeigen Sie die Ergebnisse an, und werten Sie die Genauigkeit der gefilterten Modelle analog zu den vorhergehenden drei Modellen aus.</span><span class="sxs-lookup"><span data-stu-id="a257d-143">View the results and assess the accuracy of the filtered models in much the same way as you did for the previous three models.</span></span> <span data-ttu-id="a257d-144">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="a257d-144">For more information, see:</span></span>  
  
 [<span data-ttu-id="a257d-145">Untersuchen des Entscheidungsstruktur Modells &#40;grundlegenden Data Mining-Lernprogramm&#41;</span><span class="sxs-lookup"><span data-stu-id="a257d-145">Exploring the Decision Tree Model &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/exploring-the-decision-tree-model-basic-data-mining-tutorial.md)  
  
 [<span data-ttu-id="a257d-146">Überprüfen der Genauigkeit mit Prognosegütediagrammen &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="a257d-146">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
#### <a name="to-explore-the-filtered-models"></a><span data-ttu-id="a257d-147">So untersuchen Sie die gefilterten Modelle</span><span class="sxs-lookup"><span data-stu-id="a257d-147">To explore the filtered models</span></span>  
  
1.  <span data-ttu-id="a257d-148">Wählen Sie im **Data Mining-Designer**die Registerkarte **Mining Modell-Viewer** aus.</span><span class="sxs-lookup"><span data-stu-id="a257d-148">Select the **Mining Model Viewer** tab in **Data Mining Designer**.</span></span>  
  
2.  <span data-ttu-id="a257d-149">Wählen Sie im Feld Mining Modell die Option aus `TM_Decision_Tree_Male` .</span><span class="sxs-lookup"><span data-stu-id="a257d-149">In the Mining Model box, select `TM_Decision_Tree_Male`.</span></span>  
  
3.  <span data-ttu-id="a257d-150">Folie **zeigt die Ebene** auf an `3` .</span><span class="sxs-lookup"><span data-stu-id="a257d-150">Slide **Show Level** to `3`.</span></span>  
  
4.  <span data-ttu-id="a257d-151">Ändern Sie den Wert für **Background** in `1` .</span><span class="sxs-lookup"><span data-stu-id="a257d-151">Change the **Background** value to `1`.</span></span>  
  
5.  <span data-ttu-id="a257d-152">Platzieren Sie den Cursor über dem Knoten mit der Bezeichnung **alle** , um die Anzahl der Fahrrad Käufer im Vergleich zu nicht Fahrrad Käufern anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a257d-152">Place your cursor over the node labeled **All** to see the number of bike buyers versus non-bike buyers.</span></span>  
  
6.  <span data-ttu-id="a257d-153">Wiederholen Sie die Schritte 1-5 für `TM_Decision_Tree_Female` .</span><span class="sxs-lookup"><span data-stu-id="a257d-153">Repeat steps 1 - 5 for `TM_Decision_Tree_Female`.</span></span>  
  
7.  <span data-ttu-id="a257d-154">Untersuchen Sie die Ergebnisse für die `TM_Decision_Tree` und die Modelle, die nach Geschlecht gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="a257d-154">Explore the results for the `TM_Decision_Tree` and the models filtered for gender.</span></span> <span data-ttu-id="a257d-155">Im Vergleich zu allen Fahrradkäufern weisen männliche und weibliche Fahrradkäufer einige Gemeinsamkeiten sowie drei interessante Unterschiede auf.</span><span class="sxs-lookup"><span data-stu-id="a257d-155">Compared to all bike buyers, male and female bike buyers share some of the same characteristics as the unfiltered bike buyers but all three have interesting differences as well.</span></span> <span data-ttu-id="a257d-156">Dies sind nützliche Informationen, die [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] Sie verwenden können, um Ihre Marketingkampagne zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="a257d-156">This is useful information that [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] can use to develop their marketing campaign.</span></span>  
  
#### <a name="to-test-the-lift-of-the-filtered-models"></a><span data-ttu-id="a257d-157">So testen Sie den Lift für die gefilterten Modelle</span><span class="sxs-lookup"><span data-stu-id="a257d-157">To test the lift of the filtered models</span></span>  
  
1.  <span data-ttu-id="a257d-158">Wechseln Sie in zur Registerkarte **Mining Genauigkeits Diagramm** im Data Mining-Designer, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] und wählen Sie die Registerkarte **Eingabeauswahl** aus.</span><span class="sxs-lookup"><span data-stu-id="a257d-158">Switch to the **Mining Accuracy Chart** tab in Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and select the **Input Selection** tab.</span></span>  
  
2.  <span data-ttu-id="a257d-159">Wählen Sie im Gruppenfeld Dataset **auswählen, das für das Genauigkeits Diagramm verwendet werden soll** die Option **Testfälle für Mining Struktur verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="a257d-159">In the **Select data set to be used for Accuracy Chart** group box, select **Use mining structure test cases**.</span></span>  
  
3.  <span data-ttu-id="a257d-160">Aktivieren Sie auf der Registerkarte **Eingabeauswahl** des Data Mining-Designers unter **Wählen Sie die vorhersagbaren Mining Modell Spalten**aus, die im Prognose Prognose Diagramm angezeigt werden sollen das Kontrollkästchen **Vorhersage Spalten und-Werte synchronisieren**.</span><span class="sxs-lookup"><span data-stu-id="a257d-160">On the **Input Selection** tab of Data Mining Designer, under **Select predictable mining model columns to show in the lift chart**, select the checkbox for **Synchronize Prediction Columns and Values**.</span></span>  
  
4.  <span data-ttu-id="a257d-161">Überprüfen Sie in der Spalte **Name der vorhersagbaren Spalte** , ob **Bike Buyer** für jedes Modell ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a257d-161">In the **Predictable Column Name** column, verify that **Bike Buyer** is selected for each model.</span></span>  
  
5.  <span data-ttu-id="a257d-162">Wählen Sie in der Spalte **anzeigen** die einzelnen Modelle aus.</span><span class="sxs-lookup"><span data-stu-id="a257d-162">In the **Show** column, select each of the models.</span></span>  
  
6.  <span data-ttu-id="a257d-163">Wählen Sie in der Spalte **Wert vorhersagen** aus `1` .</span><span class="sxs-lookup"><span data-stu-id="a257d-163">In the **Predict Value** column, select `1`.</span></span>  
  
7.  <span data-ttu-id="a257d-164">Wählen Sie die Registerkarte **Lift Chart** aus, um das Lift-Diagramm anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a257d-164">Select the **Lift Chart** tab to display the lift chart.</span></span>  
  
     <span data-ttu-id="a257d-165">Wie Sie sehen, weisen alle drei Entscheidungsstrukturmodelle verglichen mit dem Zufallsvorhersagemodell einen deutlichen Anstieg auf und übertreffen das Clustering- und das Naive Bayes-Modell.</span><span class="sxs-lookup"><span data-stu-id="a257d-165">You will now notice that all three Decision Tree models provide significant lift compared to the random guess model, and also outperform the Clustering and Naive-Bayes models.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a257d-166">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="a257d-166">Related Tasks</span></span>  
 <span data-ttu-id="a257d-167">Weitere Informationen zu Filtern finden Sie unter [Filter für Mining Modelle &#40;Analysis Services Data Mining-&#41;](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="a257d-167">For more information on filters, see [Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="a257d-168">Ein Beispiel für das Anwenden von Filtern auf eine Reihe von Tabellen finden Sie unter Data Mining-Lernprogramm für fort [geschrittene &#40;Analysis Services Data Mining-&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="a257d-168">For an example of how to apply filters to nested tables, see [Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md).</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="a257d-169">Vorherige Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="a257d-169">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="a257d-170">Überprüfen der Genauigkeit mit Prognosegütediagrammen &#40;Lernprogramm zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="a257d-170">Testing Accuracy with Lift Charts &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/testing-accuracy-with-lift-charts-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="a257d-171">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="a257d-171">Next Lesson</span></span>  
 [<span data-ttu-id="a257d-172">Lektion 6: Erstellen und Verwenden von Vorhersagen &#40;Tutorial zu Data Mining-Grundlagen&#41;</span><span class="sxs-lookup"><span data-stu-id="a257d-172">Lesson 6: Creating and Working with Predictions &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-6-creating-and-working-with-predictions-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="a257d-173">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a257d-173">See Also</span></span>  
 <span data-ttu-id="a257d-174">[Data Mining-Lernprogramm für fortgeschrittene &#40;Analysis Services-Data Mining-&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="a257d-174">[Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="a257d-175">[Mining Modell Tasks und Anleitungen](../../2014/analysis-services/data-mining/mining-model-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="a257d-175">[Mining Model Tasks and How-tos](../../2014/analysis-services/data-mining/mining-model-tasks-and-how-tos.md) </span></span>  
 <span data-ttu-id="a257d-176">[Löschen eines Filters aus einem Mining Modell](../../2014/analysis-services/data-mining/delete-a-filter-from-a-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="a257d-176">[Delete a Filter from a Mining Model](../../2014/analysis-services/data-mining/delete-a-filter-from-a-mining-model.md) </span></span>  
 [<span data-ttu-id="a257d-177">Filter für Miningmodelle &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="a257d-177">Filters for Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md)  
  
  
