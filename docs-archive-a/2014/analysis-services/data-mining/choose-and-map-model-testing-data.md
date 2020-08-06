---
title: Auswählen und Zuordnen von Modell Test Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- columns [data mining], mining accuracy charts
- Mining Accuracy Chart [Analysis Services], column mappings
- input column mapping [Analysis Services]
- mapping input columns [Analysis Services]
ms.assetid: be0d9f20-40c3-4dac-81da-281cfe724126
author: minewiskan
ms.author: owend
ms.openlocfilehash: 84f1d01c40070069d610bb028ab003223c5afbcd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616845"
---
# <a name="choose-and-map-model-testing-data"></a><span data-ttu-id="b72e7-102">Auswählen und Zuordnen von Modelltestdaten</span><span class="sxs-lookup"><span data-stu-id="b72e7-102">Choose and Map Model Testing Data</span></span>
  <span data-ttu-id="b72e7-103">Um in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]ein Genauigkeitsdiagramm zu erstellen, müssen Sie die Daten auswählen, die zum Testen des Modells verwendet werden und die Daten dem Modell zuordnen.</span><span class="sxs-lookup"><span data-stu-id="b72e7-103">To create an accuracy chart in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], you must choose the data that will be used to test the model, and map the data to the model.</span></span>  
  
 <span data-ttu-id="b72e7-104">Standardmäßig verwendet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] die Miningmodelltestdaten, vorausgesetzt, dass bei der Erstellung der Miningstruktur ein zurückgehaltenes Dataset erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b72e7-104">By default, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will use the mining model testing data, provided that you created a holdout data set when you built the mining structure.</span></span> <span data-ttu-id="b72e7-105">Die Erstellung eines zurückgehaltenen Testsatzes ist die einfachste Möglichkeit, Modelle zu testen, die auf der gleichen Miningstruktur basieren, da die Spaltennamen und Datentypen immer dem Modell entsprechen, und Sie können davon ausgehen, dass die Verteilung der Daten auf ähnliche Weise erfolgt.</span><span class="sxs-lookup"><span data-stu-id="b72e7-105">Creating a holdout test set is the easiest way to test models that are based on the same mining structure, because the column names and data types will always match the model, and you can be reasonably assured that the distribution of the data is similar.</span></span> <span data-ttu-id="b72e7-106">Außerdem erstellt der Designer die Beziehungen zwischen den Eingabe- und Modellspalten automatisch.</span><span class="sxs-lookup"><span data-stu-id="b72e7-106">Also, the designer will automatically create the relationships between the input and model columns.</span></span>  
  
 <span data-ttu-id="b72e7-107">Alternativ können Sie eine externe Datenquelle angeben.</span><span class="sxs-lookup"><span data-stu-id="b72e7-107">Alternatively, you can specify an external source of data.</span></span> <span data-ttu-id="b72e7-108">Für externe Daten gelten einige zusätzliche Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="b72e7-108">For external data, there are some additional requirements:</span></span>  
  
-   <span data-ttu-id="b72e7-109">Das externe Dataset muss in einer Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]als Datenquellensicht definiert werden.</span><span class="sxs-lookup"><span data-stu-id="b72e7-109">The external data set must be defined as a data source view in an instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="b72e7-110">Das externe Dataset muss mindestens eine Spalte enthalten, die der vorhersagbaren Spalte im Miningmodell zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b72e7-110">The external data set must at least contain one column that can be mapped to the predictable column in the mining model.</span></span> <span data-ttu-id="b72e7-111">Sie können einige Spalten ignorieren.</span><span class="sxs-lookup"><span data-stu-id="b72e7-111">You can choose to ignore some columns.</span></span>  
  
-   <span data-ttu-id="b72e7-112">Sie können keine neuen Spalten hinzufügen oder zuordnen, die sich in einer anderen Datenquellensicht befinden.</span><span class="sxs-lookup"><span data-stu-id="b72e7-112">You cannot add new columns or map columns in a different data source view.</span></span> <span data-ttu-id="b72e7-113">Die ausgewählte Datenquellensicht muss alle Spalten enthalten, die Sie für die Vorhersageabfrage benötigen.</span><span class="sxs-lookup"><span data-stu-id="b72e7-113">The data source view that you select must contain all the columns that you need for the prediction query.</span></span>  
  
-   <span data-ttu-id="b72e7-114">Wenn die externen Spaltennamen genau den Namen im Modell entsprechen, ordnet der Designer sie für Sie zu.</span><span class="sxs-lookup"><span data-stu-id="b72e7-114">If the external column names exactly match those in the model, the designer will map them for you.</span></span> <span data-ttu-id="b72e7-115">Wenn die Zuordnungen falsch sind, können Sie sie ändern bzw. löschen und neue Zuordnungen für vorhandene Spalten erstellen.</span><span class="sxs-lookup"><span data-stu-id="b72e7-115">If the mappings are wrong, you can change them, or delete and create new mappings for existing columns.</span></span>  
  
-   <span data-ttu-id="b72e7-116">Wenn Sie eine externe Datenquelle verwenden, können Sie Filter anwenden, um die Testdaten auf eine relevante Teilmenge von Fällen zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="b72e7-116">If you use an external data source, you can apply filters to restrict the testing data to a relevant subset of cases.</span></span>  
  
-   <span data-ttu-id="b72e7-117">Auch wenn Sie den zurückgehaltenen Testsatz verwenden, beachten Sie, dass Filter Unterschiede zwischen den Testdaten verursachen können, die einer Miningstruktur und den Miningmodelltestfällen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="b72e7-117">Even when you use the holdout test set, you should be aware that filters can cause differences between the testing data associated with a mining structure and the mining model test cases.</span></span>  
  
 <span data-ttu-id="b72e7-118">In diesem Thema wird beschrieben, wie die Testdaten ausgewählt und zugeordnet werden:</span><span class="sxs-lookup"><span data-stu-id="b72e7-118">This topic describes how to choose and map the testing data:</span></span>  
  
 [<span data-ttu-id="b72e7-119">Auswählen von Eingabetabellen zum Testen der Genauigkeit eines Miningmodells</span><span class="sxs-lookup"><span data-stu-id="b72e7-119">Select input tables to test the accuracy of a mining model</span></span>](#bkmk_SelectInputs)  
  
 [<span data-ttu-id="b72e7-120">Zuordnen von Modellspalten zu den Spalten in den Testdaten</span><span class="sxs-lookup"><span data-stu-id="b72e7-120">Map model columns to the columns in the testing data</span></span>](#bkmk_MapColumns)  
  
 [<span data-ttu-id="b72e7-121">Ändern der Methode für die Zuordnung von Spalten in den Testdaten zum Modell</span><span class="sxs-lookup"><span data-stu-id="b72e7-121">Change the way that columns in the testing data are mapped to the model</span></span>](#bkmk_ChangeMappings)  
  
##  <a name="to-select-input-tables-to-test-the-accuracy-of-a-mining-model"></a><a name="bkmk_SelectInputs"></a> <span data-ttu-id="b72e7-122">So wählen Sie Eingabetabellen zum Testen der Genauigkeit eines Miningmodells aus</span><span class="sxs-lookup"><span data-stu-id="b72e7-122">To select input tables to test the accuracy of a mining model</span></span>  
  
1.  <span data-ttu-id="b72e7-123">Doppelklicken Sie im Data Mining-Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]auf die Miningstruktur, die das Modell enthält, das Sie darstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="b72e7-123">In Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], double-click the mining structure that contains the models you want to chart.</span></span>  
  
2.  <span data-ttu-id="b72e7-124">Klicken Sie auf die Registerkarte **Mininggenauigkeitsdiagramm** .</span><span class="sxs-lookup"><span data-stu-id="b72e7-124">Select the **Mining Accuracy Chart** tab.</span></span>  
  
3.  <span data-ttu-id="b72e7-125">Wählen Sie auf der Registerkarte **Eingabeauswahl** der Sicht **Mininggenauigkeitsdiagramm** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="b72e7-125">On the **Input Selection Tab** of the **Mining Accuracy Chart** view, select one of the following options:</span></span>  
  
     <span data-ttu-id="b72e7-126">**Testfälle für Miningmodell verwenden**</span><span class="sxs-lookup"><span data-stu-id="b72e7-126">**Use mining model test cases**</span></span>  
  
     <span data-ttu-id="b72e7-127">**Testfälle für Miningstruktur verwenden**</span><span class="sxs-lookup"><span data-stu-id="b72e7-127">**Use mining structure test cases**</span></span>  
  
     <span data-ttu-id="b72e7-128">**Anderes Dataset verwenden**</span><span class="sxs-lookup"><span data-stu-id="b72e7-128">**Specify a different data set**</span></span>  
  
4.  <span data-ttu-id="b72e7-129">Wenn Sie **Anderes Dataset verwenden**auswählen, können Sie optional auf **Filter-Editor öffnen** klicken, um Filterbedingungen für das Eingabedataset zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b72e7-129">If you selected **Specify a different data set**, optionally click **Open Filter Editor** to create filter conditions on the input data set.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="b72e7-130">Klicken Sie auf die Registerkarte **Prognosegütediagramm** oder **Klassifikationsmatrix** , um die von Ihnen festgelegten Testdaten für die automatische Erstellung des Diagramms zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b72e7-130">Click the **Lift Chart** tab or the **Classification Matrix** tab to automatically build the chart by using the testing data you specified.</span></span>  
  
##  <a name="to-map-model-columns-to-the-columns-in-the-testing-data"></a><a name="bkmk_MapColumns"></a> <span data-ttu-id="b72e7-131">So ordnen Sie Modellspalten den Spalten in den Testdaten zu</span><span class="sxs-lookup"><span data-stu-id="b72e7-131">To map model columns to the columns in the testing data</span></span>  
  
1.  <span data-ttu-id="b72e7-132">Doppelklicken Sie auf die Miningstruktur, die das Modell enthält, das Sie darstellen möchten. Daraufhin werden die Struktur und die Modelle im Data Mining-Designer geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b72e7-132">Double-click the mining structure that contains the models you want to chart, to open the structure and models in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="b72e7-133">Wählen Sie die Registerkarte **Mininggenauigkeitsdiagramm** und anschließend die Registerkarte **Eingabeauswahl** aus.</span><span class="sxs-lookup"><span data-stu-id="b72e7-133">Select the **Mining Accuracy Chart** tab, and then select the **Input Selection** tab.</span></span>  
  
3.  <span data-ttu-id="b72e7-134">Wählen Sie auf der Registerkarte **Eingabeauswahl** unter **Dataset auswählen, das für das Genauigkeitsdiagramm verwendet werden soll**die Option **Anderes Dataset verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="b72e7-134">In the **Input Selection** tab, under **Select data set to be used for Accuracy Chart**, select **Specify a different data set**.</span></span>  
  
4.  <span data-ttu-id="b72e7-135">Klicken Sie auf die Schaltfläche zum Durchsuchen **(...)** , um ein Dialogfeld zu öffnen und die Definition des externen Datasets zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b72e7-135">Click the browse button **(...)** to open a dialog box and build the definition of the external data set.</span></span>  
  
5.  <span data-ttu-id="b72e7-136">Wählen Sie im Dialogfeld **Miningstruktur auswählen** die Miningstruktur aus, mit der Sie arbeiten wollen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b72e7-136">In the **Select Mining Structure** dialog box, select the mining structure that contains the models you want to work with, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="b72e7-137">Klicken Sie im Data Mining-Designer in der Tabelle **Eingabetabelle(n) auswählen** der Registerkarte **Mininggenauigkeitsdiagramm** auf **Falltabelle auswählen** , um das Dialogfeld **Falltabelle auswählen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b72e7-137">On the **Select Input Table(s)** table of the **Mining Accuracy Chart** tab, click **Select Case Table** to open the **Select Table** dialog box.</span></span>  
  
7.  <span data-ttu-id="b72e7-138">Wählen Sie im Dialogfeld **Tabelle auswählen** in der Liste **Datenquelle** eine Datenquelle aus.</span><span class="sxs-lookup"><span data-stu-id="b72e7-138">In the **Select Table** dialog box, select a data source from the **Data Source** list.</span></span> <span data-ttu-id="b72e7-139">Wählen Sie die Tabelle mit den Daten aus, die Sie in den Vorhersageabfragen verwenden möchten, mit denen die Genauigkeit der Modelle ermittelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b72e7-139">Choose a table that contains the data that you want to use in the prediction queries to determine the accuracy of the models.</span></span>  
  
8.  <span data-ttu-id="b72e7-140">Wählen Sie im Feld **Tabellen-/Sichtname** die Tabelle aus, die die Daten enthält, die zum Testen der Modelle verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b72e7-140">In the **Table/View Name** box, select the table that contains the data that you want to use to test the models.</span></span>  
  
9. <span data-ttu-id="b72e7-141">Bearbeiten Sie gegebenenfalls die Zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="b72e7-141">Edit the mappings, if necessary.</span></span> <span data-ttu-id="b72e7-142">Die Spalten der Miningstruktur werden automatisch den gleichnamigen Spalten der Eingabetabelle zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="b72e7-142">Columns in the mining structure are automatically mapped to the columns with the same name in the input table.</span></span> <span data-ttu-id="b72e7-143">Um Zuordnungen manuell zu erstellen, klicken Sie in der Tabelle **Eingabetabelle(n) auswählen** auf eine Spalte, und ziehen Sie diese auf die entsprechende Spalte der Tabelle **Miningstruktur** .</span><span class="sxs-lookup"><span data-stu-id="b72e7-143">To manually create mappings, click a column in the **Select Input Table(s)** table and drag it onto the corresponding column in the **Mining Structure** table.</span></span> <span data-ttu-id="b72e7-144">Um eine Zuordnung zu löschen, klicken Sie auf die Linie, die die Spalte der Tabelle **Miningstruktur** mit der Spalte der Tabelle **Eingabetabelle(n) auswählen** verbindet, und drücken Sie dann ENTF.</span><span class="sxs-lookup"><span data-stu-id="b72e7-144">To delete a mapping, click the line that links the column in the **Mining Structure** table to the mapped column in the **Select Input Table(s)** table, and then press DELETE.</span></span>  
  
10. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="to-modify-the-way-input-data-is-mapped-to-the-model"></a><a name="bkmk_ChangeMappings"></a><span data-ttu-id="b72e7-145">So ändern Sie die Art der Zuordnung von Eingabedaten zum Modell</span><span class="sxs-lookup"><span data-stu-id="b72e7-145">To modify the way input data is mapped to the model</span></span>  
  
1.  <span data-ttu-id="b72e7-146">Doppelklicken Sie im Data Mining-Designer auf die Struktur mit den Modellen, die Sie im Diagramm darstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="b72e7-146">In Data Mining Designer, double-click the structure that contains the models you want to chart.</span></span>  
  
2.  <span data-ttu-id="b72e7-147">Klicken Sie auf die Registerkarte **Mininggenauigkeitsdiagramm** .</span><span class="sxs-lookup"><span data-stu-id="b72e7-147">Select the **Mining Accuracy Chart** tab.</span></span>  
  
3.  <span data-ttu-id="b72e7-148">Klicken Sie auf die Registerkarte **Eingabeauswahl** .</span><span class="sxs-lookup"><span data-stu-id="b72e7-148">Click the **Input Selection** tab.</span></span>  
  
4.  <span data-ttu-id="b72e7-149">Wählen Sie unter DataSet **auswählen, das für das Genauigkeits Diagramm verwendet werden soll**die Option anderes DataSet **angeben**aus.</span><span class="sxs-lookup"><span data-stu-id="b72e7-149">In **Select data set to be used for Accuracy Chart**, select the option **Specify a different data set**.</span></span>  
  
5.  <span data-ttu-id="b72e7-150">Klicken Sie auf die Schaltfläche zum Durchsuchen **(...)** , um ein Dialogfeld zu öffnen und die Definition der externen Datenquelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b72e7-150">Click the browse button **(...)** to open a dialog box and build the definition of the external data source.</span></span>  
  
6.  <span data-ttu-id="b72e7-151">Klicken Sie im Dialogfeld **Spaltenzuordnung angeben** auf **Falltabelle auswählen**.</span><span class="sxs-lookup"><span data-stu-id="b72e7-151">In the **Specify Column Mapping** dialog box, click **Select Case Table**.</span></span>  
  
7.  <span data-ttu-id="b72e7-152">Wählen Sie im Dialogfeld Tabelle auswählen eine Datenquellensicht aus der Liste aus, und wählen Sie dann die Tabelle aus, die die Falldaten enthält.</span><span class="sxs-lookup"><span data-stu-id="b72e7-152">In the Select Table dialog box, Select a data source view from the list, and select the table that contains the case data.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="b72e7-153">Wenn die benötigten Tabellen nicht verfügbar sind, schließen Sie das Dialogfeld, und erstellen Sie eine neue Datenquellensicht, die die Tabelle enthält.</span><span class="sxs-lookup"><span data-stu-id="b72e7-153">If the tables you need are not available, close the dialog box and create a new data source view that contains the table.</span></span> <span data-ttu-id="b72e7-154">Informationen zum Erstellen einer Datenquellensicht finden Sie unter [Definieren einer Datenquellensicht &#40;Analysis Services&#41;](../multidimensional-models/defining-a-data-source-view-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="b72e7-154">For information about how to create a data source view, see [Defining a Data Source View &#40;Analysis Services&#41;](../multidimensional-models/defining-a-data-source-view-analysis-services.md).</span></span>  
  
9. <span data-ttu-id="b72e7-155">Wenn das Miningmodell eine geschachtelte Tabelle enthält, klicken Sie auf **Geschachtelte Tabelle auswählen**, und wählen Sie die geschachtelte Tabelle aus der Liste der Tabellen in der Datenquellensicht aus.</span><span class="sxs-lookup"><span data-stu-id="b72e7-155">If the mining model contains a nested table, click **Select Nested Table**, and select the nested table from the list of tables in the data source view.</span></span> [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
10. <span data-ttu-id="b72e7-156">Wählen Sie die Joinlinie der Zuordnung aus, die Sie ändern möchten, und wählen Sie **Verbindungen ändern**aus.</span><span class="sxs-lookup"><span data-stu-id="b72e7-156">Select the join line of the mapping you want to modify, and select **Modify Connections**.</span></span>  
  
     <span data-ttu-id="b72e7-157">Das Dialogfeld **Zuordnung bearbeiten** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b72e7-157">The **Modify Mapping** dialog box opens.</span></span> <span data-ttu-id="b72e7-158">In der Tabelle in diesem Dialogfeld werden unter **Miningstrukturspalte** alle Spalten aufgeführt, die die ausgewählte Miningstruktur enthalten. Unter **Tabellenspalte** werden die Spalten aus Eingabetabellen aufgelistet, die Spalten in der Miningstruktur zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="b72e7-158">In the table in this dialog box, **Mining Structure Column** lists each column that the selected mining structure contains, and **Table Column** lists the columns from input tables that are mapped to columns in the mining structure.</span></span>  
  
11. <span data-ttu-id="b72e7-159">Wählen Sie unter **Tabellenspalte**die Zeile aus, die der Zeile unter **Miningstrukturspalte** entspricht, für die Sie eine Beziehung ändern wollen.</span><span class="sxs-lookup"><span data-stu-id="b72e7-159">Under **Table Column**, select the row that corresponds to the row under **Mining Structure Column** for which you want to modify a relationship.</span></span> <span data-ttu-id="b72e7-160">Wählen Sie eine neue Spalte in der Liste aus, oder wählen Sie den leeren Eintrag in der Liste aus, um die Spalte zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b72e7-160">Select a new column from the list, or select the blank entry from the list to delete the column.</span></span>  
  
12. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
     <span data-ttu-id="b72e7-161">Die neuen Spaltenzuordnungen werden im Dialogfeld **Spaltenzuordnung angeben** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b72e7-161">The new column mappings are displayed in the **Specify Column Mapping** dialog box.</span></span> <span data-ttu-id="b72e7-162">Sie können eine Zuordnung entfernen, indem Sie die Linie zwischen den Spalten auswählen und die ENTF-Taste drücken.</span><span class="sxs-lookup"><span data-stu-id="b72e7-162">You can remove a mapping by selecting the line between the columns and pressing the DELETE key.</span></span> <span data-ttu-id="b72e7-163">Sie können eine neue Verbindung erstellen, indem Sie in der **Miningstruktur** -Tabelle eine Spalte auswählen und diese Spalte auf die entsprechende Spalte in der **Eingabetabelle(n) auswählen** -Tabelle ziehen.</span><span class="sxs-lookup"><span data-stu-id="b72e7-163">You can create a new connection by selecting a column in the **Mining Structure** table and dragging it to the corresponding column in the **SelectInput Table(s)** table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b72e7-164">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b72e7-164">See Also</span></span>  
 [<span data-ttu-id="b72e7-165">Tasks und Anweisungen für Test und Überprüfung &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="b72e7-165">Testing and Validation Tasks and How-tos &#40;Data Mining&#41;</span></span>](testing-and-validation-tasks-and-how-tos-data-mining.md)  
  
  
