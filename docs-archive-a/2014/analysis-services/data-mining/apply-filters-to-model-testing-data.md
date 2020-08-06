---
title: Anwenden von Filtern zum Modellieren von Testdaten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input row filtering [SQL Server]
- filtering input rows [Analysis Services]
- Mining Accuracy Chart [Analysis Services], filtering input rows
ms.assetid: 9ccc9a23-5597-4b35-a05f-2fc8eb885147
author: minewiskan
ms.author: owend
ms.openlocfilehash: d1fd2b643ae4f7d831cab980ca45b7d43d8b58f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608933"
---
# <a name="apply-filters-to-model-testing-data"></a><span data-ttu-id="2824c-102">Anwenden von Filtern zum Modellieren von Testdaten</span><span class="sxs-lookup"><span data-stu-id="2824c-102">Apply Filters to Model Testing Data</span></span>
  <span data-ttu-id="2824c-103">Wenn Sie eine externe Datenquelle angeben, die beim Testen eines verwendet werden soll, können Sie optional einen Filter anwenden, um die Eingabedaten einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="2824c-103">When you specify an external data source to use in testing a model, you can optionally apply a filter to restrict the input data.</span></span> <span data-ttu-id="2824c-104">Sie möchten das Modell zum Beispiel speziell für Vorhersagen zu Kunden in einem bestimmten Einkommensbereich testen.</span><span class="sxs-lookup"><span data-stu-id="2824c-104">For example, you might want to test the model specifically for predictions on customers in a certain income range.</span></span>  
  
 <span data-ttu-id="2824c-105">Beispielsweise können Sie im Szenario "AdventureWorks-Ziel Mailing" einen Filter Ausdruck wie den folgenden für "ProspectiveBuyer" erstellen, bei dem es sich um die Tabelle handelt, die die Testdaten enthält, und die Testfälle nach Einkommensbereich einschränken:</span><span class="sxs-lookup"><span data-stu-id="2824c-105">For example, in the AdventureWorks targeted mailing scenario, you can create a filter expression like the following one on ProspectiveBuyer, which is the table that contains the testing data, and restrict testing cases by income range:</span></span>  
  
 `[YearlyIncome] = '50000'`  
  
 <span data-ttu-id="2824c-106">Das Verhalten von Filtern unterscheidet sich ein wenig, was davon abhängig ist, ob Sie Modelltrainingsdaten oder ein Testdataset filtern:</span><span class="sxs-lookup"><span data-stu-id="2824c-106">The behavior of filters is slightly different, depending on whether you are filtering model training data or a testing data set:</span></span>  
  
-   <span data-ttu-id="2824c-107">Wenn Sie einen Filter für ein Testdataset definieren, erstellen Sie eine WHERE-Klausel für die eingehenden Daten.</span><span class="sxs-lookup"><span data-stu-id="2824c-107">When you define a filter on a testing data set, you create a WHERE clause on the incoming data.</span></span> <span data-ttu-id="2824c-108">Wenn ein zum Auswerten des Modells verwendetes Eingabedataset gefiltert wird, wird der Filterausdruck in eine Transact-SQL-Anweisung übersetzt und bei der Diagrammerstellung auf die Eingabetabelle angewendet.</span><span class="sxs-lookup"><span data-stu-id="2824c-108">If you are filtering an input data set used for evaluating a model, the filter expression is translated to a Transact-SQL statement and applied to the input table when the chart is created.</span></span> <span data-ttu-id="2824c-109">Dadurch kann die Anzahl von Testfällen stark verringert werden.</span><span class="sxs-lookup"><span data-stu-id="2824c-109">As a result, the number of test cases can be greatly reduced.</span></span>  
  
-   <span data-ttu-id="2824c-110">Wenn Sie einen Filter auf ein Miningmodell anwenden, wird der von Ihnen definierte Filterausdruck in eine DMX-Anweisung (Data Mining Extensions) übersetzt und auf das einzelne Modell angewendet.</span><span class="sxs-lookup"><span data-stu-id="2824c-110">When you apply a filter to a mining model, the filter expression that you create is translated to a Data Mining Extensions (DMX) statement, and applied to the individual model.</span></span> <span data-ttu-id="2824c-111">Daher wird beim Anwenden eines Filters auf ein Modell nur eine Teilmenge der ursprünglichen Daten zum Trainieren des Modells verwendet.</span><span class="sxs-lookup"><span data-stu-id="2824c-111">Therefore, when you apply a filter to a model, only a subset of the original data is used to train the model.</span></span> <span data-ttu-id="2824c-112">Dies kann Probleme verursachen, wenn Sie das Trainingsmodell mit einem Kriteriensatz filtern, damit das Modell im Hinblick auf einen bestimmten Satz von Daten optimiert wird, und anschließend das Modell mit einem anderen Satz von Kriterien testen.</span><span class="sxs-lookup"><span data-stu-id="2824c-112">This can cause problems if you filter the training model with one set of criteria, so that the model is tuned to a certain set of data, and then test the model with another set of criteria.</span></span>  
  
-   <span data-ttu-id="2824c-113">Wenn beim Erstellen der Struktur ein Testdataset definiert wurde, umfassen die zum Training verwendeten Modellfälle nur die Fälle, die im Trainingssatz der Miningstruktur enthalten sind **und** den Filterbedingungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2824c-113">If you defined a testing data set when you created the structure, the model cases used for training include only those cases that are in the mining structure training set **and** which meet the conditions of the filter.</span></span> <span data-ttu-id="2824c-114">Wenn Sie ein Modell testen und die Option **Testfälle für Miningstruktur verwenden**auswählen, beinhalten die Testfälle daher nur die Fälle, die im Testsatz der Miningstruktur enthalten sind und den Filterbedingungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2824c-114">Thus, when you are testing a model and select the option **Use mining model test cases**, the testing cases will include only the cases that are in the mining structure test set and which meet the conditions of the filter.</span></span> <span data-ttu-id="2824c-115">Wenn das Zurückhaltungsdataset nicht definiert wurde, werden alle Modellfälle, die den Filterbedingungen entsprechen, zum Training verwendet.</span><span class="sxs-lookup"><span data-stu-id="2824c-115">However, if you did not define a holdout data set, the model cases used for testing include all the cases in the data set that meet the filter conditions</span></span>  
  
-   <span data-ttu-id="2824c-116">Filterbedingungen, die Sie für ein Modell übernehmen, beeinflussen auch Drillthroughabfragen für die Modellfälle.</span><span class="sxs-lookup"><span data-stu-id="2824c-116">Filter conditions that you apply on a model also affect drillthrough queries on the model cases.</span></span>  
  
 <span data-ttu-id="2824c-117">Zusammenfassung: Wenn Sie mehrere Modelle testen, auch wenn alle Modelle auf der gleichen Miningstruktur basieren, müssen Sie sich darüber im Klaren sein, dass die Modelle für Training und Tests möglicherweise andere Teilmengen von Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="2824c-117">In summary, when you test multiple models, even if all the models are based on the same mining structure, you must be aware that the models potentially use different subsets of data for training and testing.</span></span> <span data-ttu-id="2824c-118">Dies kann folgende Auswirkungen auf Genauigkeitsdiagramme haben:</span><span class="sxs-lookup"><span data-stu-id="2824c-118">This can have the following effects on accuracy charts:</span></span>  
  
-   <span data-ttu-id="2824c-119">Die Gesamtzahl der Fälle in den Testsätzen kann sich je nach getestetem Modell unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="2824c-119">The total number of cases in the testing sets can vary among the models being tested.</span></span>  
  
-   <span data-ttu-id="2824c-120">Die Prozentsätze für jedes Modell ergeben im Diagramm möglicherweise keine Übereinstimmung, wenn die Modelle unterschiedliche Teilmengen von Trainings- oder Testdaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="2824c-120">The percentages for each model may not align in the chart, if the models use different subsets of training data or testing data.</span></span>  
  
 <span data-ttu-id="2824c-121">Um zu bestimmen, ob ein Modell einen vordefinierten Filter enthält, der sich auf die Ergebnisse auswirken könnte, können Sie nach der **Filter** -Eigenschaft im **Eigenschaftenbereich** suchen, oder Sie können das Modell abfragen, indem Sie die Data Mining-Schemarowsets verwenden.</span><span class="sxs-lookup"><span data-stu-id="2824c-121">To determine whether a model contains a predefined filter that might affect results, you can look for the **Filter** property in the **Property** pane, or you can query the model by using the data mining schema rowsets.</span></span> <span data-ttu-id="2824c-122">Zum Beispiel wird bei der folgenden Abfrage der Filtertext für das angegebene Modell zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="2824c-122">For example, the following query returns the filter text for the specified model:</span></span>  
  
 `SELECT [FILTER] FROM $system.DMSCHEMA_MINING_MODELS WHERE MODEL_NAME = 'name of model'`  
  
> [!WARNING]  
>  <span data-ttu-id="2824c-123">Wenn Sie den Filter aus einem vorhandenen Miningmodell entfernen oder die Filterbedingungen ändern möchten, müssen Sie das Miningmodell erneut verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2824c-123">If you want to remove the filter from an existing mining model, or change the filter conditions, you must reprocess the mining model.</span></span>  
  
 <span data-ttu-id="2824c-124">Weitere Informationen zu den Filtertypen, die angewendet werden können, und zur Auswertung von Filterausdrücken finden Sie unter [Modellfiltersyntax und Beispiele &#40;Analysis Services – Data Mining&#41;](model-filter-syntax-and-examples-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="2824c-124">For more information about the kinds of filters you can apply, and how filter expressions are evaluated, see [Model Filter Syntax and Examples &#40;Analysis Services - Data Mining&#41;](model-filter-syntax-and-examples-analysis-services-data-mining.md).</span></span>  
  
### <a name="create-a-filter-on-external-testing-data"></a><span data-ttu-id="2824c-125">Erstellen eines Filters für externe Testdaten</span><span class="sxs-lookup"><span data-stu-id="2824c-125">Create a filter on external testing data</span></span>  
  
1.  <span data-ttu-id="2824c-126">Doppelklicken Sie auf die Miningstruktur, die das Modell enthält, das Sie testen möchten, um den Data Mining-Designer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2824c-126">Double-click the mining structure that contains the model you want to test, to open Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="2824c-127">Wählen Sie die Registerkarte **Mininggenauigkeitsdiagramm** und anschließend die Registerkarte **Eingabeauswahl** aus.</span><span class="sxs-lookup"><span data-stu-id="2824c-127">Select the **Mining Accuracy Chart** tab, and then select the **Input Selection** tab.</span></span>  
  
3.  <span data-ttu-id="2824c-128">Wählen Sie auf der Registerkarte **Eingabeauswahl** unter **Dataset auswählen, das für das Genauigkeitsdiagramm verwendet werden soll**die Option **Anderes Dataset verwenden**.</span><span class="sxs-lookup"><span data-stu-id="2824c-128">On the **Input Selection** tab, under **Select data set to be used for Accuracy Chart**, select the option **Specify a different data set**.</span></span>  
  
4.  <span data-ttu-id="2824c-129">Klicken Sie auf die Schaltfläche zum Durchsuchen **(...)** , um ein Dialogfeld zu öffnen und das externe Dataset auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="2824c-129">Click the browse button **(...)** to open a dialog box and choose the external data set.</span></span>  
  
5.  <span data-ttu-id="2824c-130">Wählen Sie die Falltabelle aus, und fügen Sie ggf. eine geschachtelte Tabelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="2824c-130">Choose the case table, and add a nested table if necessary.</span></span> <span data-ttu-id="2824c-131">Ordnen Sie Spalten im Modell nach Bedarf Spalten im externen Dataset zu.</span><span class="sxs-lookup"><span data-stu-id="2824c-131">Map columns in the model to columns in the external data set as necessary.</span></span> <span data-ttu-id="2824c-132">Schließen Sie das Dialogfeld **Spaltenzuordnung angeben** , um die Quelltabellendefinition zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2824c-132">Close the **Specify Column Mapping** dialog box to save the source table definition.</span></span>  
  
6.  <span data-ttu-id="2824c-133">Klicken Sie auf **Filter-Editor öffnen** , um einen Filter für das Dataset zu definieren.</span><span class="sxs-lookup"><span data-stu-id="2824c-133">Click **Open Filter Editor** to define a filter for the data set.</span></span>  
  
     <span data-ttu-id="2824c-134">Das Dialogfeld **Datasetfilter** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="2824c-134">The **Data Set Filter** dialog box opens.</span></span> <span data-ttu-id="2824c-135">Wenn die Struktur eine geschachtelte Tabelle enthält, können Sie einen Filter in zwei Teilen erstellen.</span><span class="sxs-lookup"><span data-stu-id="2824c-135">If the structure contains a nested table, you can create a filter in two parts.</span></span> <span data-ttu-id="2824c-136">Legen Sie zuerst mithilfe des Dialogfelds **Datasetfilter** Bedingungen für die Falltabelle fest, und anschließend legen Sie Bedingungen für die geschachtelten Zeilen mithilfe des Dialogfelds **Filter** fest.</span><span class="sxs-lookup"><span data-stu-id="2824c-136">First, set conditions on the case table by using the **Data Set Filter** dialog box, and then set conditions on the nested rows by using the **Filter** dialog box.</span></span>  
  
7.  <span data-ttu-id="2824c-137">Klicken Sie im Dialogfeld **Datasetfilter** auf die oberste Zeile im Raster (unter **Miningstrukturspalte**), und wählen Sie eine Tabelle oder eine Spalte in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="2824c-137">In the **Data Set Filter** dialog box, click the top row in the grid, under **Mining Structure Column**, and select a table or column from the list.</span></span>  
  
     <span data-ttu-id="2824c-138">Wenn die Datensatzsicht mehrere Tabellen oder eine geschachtelte Tabelle enthält, müssen Sie zuerst den Tabellennamen auswählen.</span><span class="sxs-lookup"><span data-stu-id="2824c-138">If the data source view contains multiple tables, or a nested table, you must first select the table name.</span></span> <span data-ttu-id="2824c-139">Andernfalls können Sie Spalten direkt aus der Falltabelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="2824c-139">Otherwise, you can select columns from the case table directly.</span></span>  
  
     <span data-ttu-id="2824c-140">Fügen Sie eine neue Zeile für jede Spalte hinzu, die Sie filtern möchten.</span><span class="sxs-lookup"><span data-stu-id="2824c-140">Add a new row for each column that you want to filter.</span></span>  
  
8.  <span data-ttu-id="2824c-141">Verwenden Sie die Spalten **Operator**und **Wert** , um zu definieren, wie die Spalte gefiltert wird.</span><span class="sxs-lookup"><span data-stu-id="2824c-141">Use **Operator**, and **Value** columns to define how the column is filtered.</span></span>  
  
     <span data-ttu-id="2824c-142">**Hinweis** Geben Sie die Werte ohne Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="2824c-142">**Note** Type values without using quotation marks.</span></span>  
  
9. <span data-ttu-id="2824c-143">Klicken Sie auf das Textfeld **Und/Oder** , und wählen Sie einen logischen Operator aus, um zu definieren, wie mehrere Bedingungen kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="2824c-143">Click the **And/Or** text box and select a logical operator to define how multiple conditions are combine.</span></span>  
  
10. <span data-ttu-id="2824c-144">Klicken Sie optional auf die Schaltfläche zum Durchsuchen **(...)** rechts neben dem Textfeld **Wert** , um das Dialogfeld **Filter** zu öffnen und Bedingungen für die schallete Tabelle oder die einzelnen Spalten der Fall Tabelle festzulegen.</span><span class="sxs-lookup"><span data-stu-id="2824c-144">Optionally, click the browse button **(...)** at the right of the **Value** text box to open the **Filter** dialog box and set conditions on the nested table or on the individual case table columns.</span></span>  
  
11. <span data-ttu-id="2824c-145">Überprüfen Sie, dass die fertig gestellten Filterbedingungen richtig sind, indem Sie den Text im Bereich **Ausdruck** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2824c-145">Verify that the completed filter conditions are correct by viewing the text in the **Expression** pane.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="2824c-146">Die Filterbedingung wird auf die Datenquelle angewendet, wenn Sie das Genauigkeitsdiagramm erstellen.</span><span class="sxs-lookup"><span data-stu-id="2824c-146">The filter condition is applied to the data source when you create the accuracy chart.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2824c-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2824c-147">See Also</span></span>  
 <span data-ttu-id="2824c-148">[Auswählen und Zuordnen von Modell Test Daten](choose-and-map-model-testing-data.md) </span><span class="sxs-lookup"><span data-stu-id="2824c-148">[Choose and Map Model Testing Data](choose-and-map-model-testing-data.md) </span></span>  
 <span data-ttu-id="2824c-149">[Verwenden von Daten in einer Datentabelle als Eingabe für ein Genauigkeits Diagramm](using-nested-table-data-as-an-input-for-an-accuracy-chart.md) </span><span class="sxs-lookup"><span data-stu-id="2824c-149">[Using Nested Table Data as an Input for an Accuracy Chart](using-nested-table-data-as-an-input-for-an-accuracy-chart.md) </span></span>  
 [<span data-ttu-id="2824c-150">Auswählen eines Genauigkeitsdiagrammtyps Festlegen von Diagrammoptionen</span><span class="sxs-lookup"><span data-stu-id="2824c-150">Choose an Accuracy Chart Type and Set Chart Options</span></span>](choose-an-accuracy-chart-type-and-set-chart-options.md)  
  
  
