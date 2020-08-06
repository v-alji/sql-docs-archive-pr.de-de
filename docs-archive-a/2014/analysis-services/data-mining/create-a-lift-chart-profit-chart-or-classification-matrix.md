---
title: Erstellen eines Lift Diagramms, eines Gewinn Diagramms oder einer Klassifikations Matrix | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Mining Accuracy Chart [Analysis Services], mining structures
ms.assetid: aa3d052f-58a9-4417-8e7a-5e6feb562af0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 932138b37b36269bed86df42786bd5d684f75ee9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696333"
---
# <a name="create-a-lift-chart-profit-chart-or-classification-matrix"></a><span data-ttu-id="bab78-102">Erstellen von Prognosegütediagrammen, Gewinndiagrammen oder Klassifikationsmatrizen</span><span class="sxs-lookup"><span data-stu-id="bab78-102">Create a Lift Chart, Profit Chart, or Classification Matrix</span></span>
  <span data-ttu-id="bab78-103">Sie können für ein Data Mining-Modell in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] mit fünf grundlegenden Schritten ein Genauigkeitsdiagramm erstellen:</span><span class="sxs-lookup"><span data-stu-id="bab78-103">You can create an accuracy chart for an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] data mining model in five basic steps:</span></span>  
  
-   <span data-ttu-id="bab78-104">Wählen Sie die Miningstruktur aus, die die zu vergleichenden Miningmodelle enthält.</span><span class="sxs-lookup"><span data-stu-id="bab78-104">Select the mining structure that contains the mining models that you want to compare.</span></span>  
  
-   <span data-ttu-id="bab78-105">Wählen Sie die Miningmodelle aus, die dem Diagramm hinzugefügt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bab78-105">Select the mining models to add to the chart.</span></span>  
  
-   <span data-ttu-id="bab78-106">Geben Sie eine Testdatenquelle an, die beim Generieren des Diagramms verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bab78-106">Specify a source of testing data to use in generating the chart.</span></span>  
  
-   <span data-ttu-id="bab78-107">Wählen Sie den Diagrammtyp.</span><span class="sxs-lookup"><span data-stu-id="bab78-107">Choose the chart type.</span></span>  
  
-   <span data-ttu-id="bab78-108">Konfigurieren Sie die Diagrammoptionen.</span><span class="sxs-lookup"><span data-stu-id="bab78-108">Configure the chart options.</span></span>  
  
 <span data-ttu-id="bab78-109">Diese grundlegenden Schritte sind für das Prognosegütediagramm, das Gewinndiagramm und die Klassifizierungsmatrix identisch.</span><span class="sxs-lookup"><span data-stu-id="bab78-109">These basic steps are the same for the lift chart, profit chart, and classification matrix.</span></span> <span data-ttu-id="bab78-110">Die folgenden Prozeduren gliedern die Schritte zur Konfiguration der grundlegenden Diagrammoptionen für diese Diagrammtypen.</span><span class="sxs-lookup"><span data-stu-id="bab78-110">The following procedures outline the steps to configure the basic chart options for these chart types.</span></span> <span data-ttu-id="bab78-111">Informationen zum Erstellen eines übergreifenden Überprüfungsberichts finden Sie unter [Measures im Kreuzvalidierungsbericht](measures-in-the-cross-validation-report.md).</span><span class="sxs-lookup"><span data-stu-id="bab78-111">For information about how to create a cross-validation report, see [Measures in the Cross-Validation Report](measures-in-the-cross-validation-report.md).</span></span>  
  
### <a name="open-the-mining-structure-in-the-accuracy-chart-designer"></a><span data-ttu-id="bab78-112">Öffnen der Miningstruktur im Genauigkeitsdiagramm-Designer</span><span class="sxs-lookup"><span data-stu-id="bab78-112">Open the mining structure in the Accuracy Chart Designer</span></span>  
  
1.  <span data-ttu-id="bab78-113">Öffnen Sie den Data Mining-Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bab78-113">Open the Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="bab78-114">Doppelklicken Sie in Projektmappen-Explorer auf die Struktur, die das bzw. die Miningmodelle enthält.</span><span class="sxs-lookup"><span data-stu-id="bab78-114">In Solution Explorer, double-click the structure that contains the mining model or models.</span></span>  
  
3.  <span data-ttu-id="bab78-115">Klicken Sie auf die Registerkarte **Mininggenauigkeitsdiagramm** .</span><span class="sxs-lookup"><span data-stu-id="bab78-115">Click the **Mining Accuracy Chart** tab.</span></span>  
  
### <a name="select-mining-models-for-inclusion-in-the-chart"></a><span data-ttu-id="bab78-116">Auswählen von Miningmodellen für die Einbeziehung in das Diagramm</span><span class="sxs-lookup"><span data-stu-id="bab78-116">Select mining models for inclusion in the chart</span></span>  
  
1.  <span data-ttu-id="bab78-117">Klicken Sie in **auf der Registerkarte** Mininggenauigkeitsdiagramm [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]im Data Mining-Designer auf die Registerkarte **Eingabeauswahl** .</span><span class="sxs-lookup"><span data-stu-id="bab78-117">On the **Mining Accuracy Chart** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Input Selection** tab.</span></span>  
  
     <span data-ttu-id="bab78-118">Die Liste zeigt alle Modelle in der aktuellen Struktur an, die über das gleiche vorhersagbare Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="bab78-118">The list displays all models in the current structure that have the same predictable attribute.</span></span>  
  
2.  <span data-ttu-id="bab78-119">Wählen Sie das Feld **Anzeigen** für jedes Modell aus, das Sie ins Diagramm aufnehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="bab78-119">Select the **Show box** for each model that you want to include in the chart.</span></span>  
  
3.  <span data-ttu-id="bab78-120">Klicken Sie auf das Textfeld **Name der vorhersagbaren Spalte** , und wählen Sie den Namen einer vorhersagbaren Spalte in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="bab78-120">Click the **Predictable Column Name** text box, and select the name of a predictable column from the list.</span></span> <span data-ttu-id="bab78-121">Alle Modelle, die Sie in das Diagramm aufnehmen, müssen die gleiche vorhersagbare Spalte verwenden.</span><span class="sxs-lookup"><span data-stu-id="bab78-121">All models that you put in one chart must have the same predictable column.</span></span>  
  
4.  <span data-ttu-id="bab78-122">Wenn Sie zwei Modelle vergleichen und die vorhersagbaren Spalten unterschiedliche Werte oder Datentypen besitzen, deaktivieren Sie das Kontrollkästchen **Vorhersagespalten und -werte synchronisieren** , um einen Vergleich zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="bab78-122">If you compare two models and the predictable columns have different values or different data types, clear the **Synchonize prediction columns and values** box to force a comparison.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bab78-123">Ist das Kontrollkästchen **Vorhersagespalten und -werte synchronisieren** aktiviert, analysiert Analysis Services die Daten in den vorhersagbaren Spalten des Modells sowie die Testdaten und versucht, die größte Übereinstimmung zu finden.</span><span class="sxs-lookup"><span data-stu-id="bab78-123">If the **Synchonize prediction columns and values** box is selected, Analysis Services analyzes the data in the predictable columns of the model and the test data, and attempts to find the best match.</span></span> <span data-ttu-id="bab78-124">Deaktivieren Sie das Kontrollkästchen daher nur, wenn es absolut erforderlich ist, um einen Vergleich der Spalten zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="bab78-124">Therefore, do not clear the box unless absolutely necessary to force a comparison of the columns.</span></span>  
  
5.  <span data-ttu-id="bab78-125">Klicken Sie auf das Textfeld **Wert vorhersagen** , und wählen Sie einen Wert aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="bab78-125">Click the **Predict Value** text box, and select a value from the list.</span></span> <span data-ttu-id="bab78-126">Wenn die vorhersagbare Spalte einen kontinuierlichen Datentyp enthält, müssen Sie einen Wert in das Textfeld eingeben.</span><span class="sxs-lookup"><span data-stu-id="bab78-126">If the predictable column is a continuous data type, you must type a value in the text box.</span></span>  
  
     <span data-ttu-id="bab78-127">Weitere Informationen finden Sie unter [Auswählen der zum Testen eines Miningmodells zu verwendenden Spalte](choose-the-column-to-use-for-testing-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="bab78-127">For more information, see [Choose the Column to Use for Testing a Mining Model](choose-the-column-to-use-for-testing-a-mining-model.md).</span></span>  
  
### <a name="select-testing-data"></a><span data-ttu-id="bab78-128">Auswählen von Testdaten</span><span class="sxs-lookup"><span data-stu-id="bab78-128">Select testing data</span></span>  
  
1.  <span data-ttu-id="bab78-129">Geben Sie auf der Registerkarte **Eingabeauswahl** der Registerkarte **Mininggenauigkeitsdiagramm** die Datenquelle an, mit der Sie das Diagramm generieren. Wählen Sie dazu eine der Optionen in der Gruppe **Dataset auswählen, das für das Genauigkeitsdiagramm verwendet werden soll**aus.</span><span class="sxs-lookup"><span data-stu-id="bab78-129">On the **Input Selection** tab of the **Mining Accuracy Chart** tab, specify the source of the data that you will use to generate the chart by selecting one of the options in the group, **Select data set to be used for accuracy chart**.</span></span>  
  
    -   <span data-ttu-id="bab78-130">Wählen Sie die Option **Miningmodelltestfälle verwenden**, wenn Sie die Teilmenge der Fälle verwenden möchten, die von der Schnittmenge der Miningstrukturtestfälle und aller Filter definiert werden, die möglicherweise während der Modellerstellung angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="bab78-130">Select the option, **Use Mining Model test cases**, if you want to use the subset of cases that is defined by the intersection of the mining structure test cases and any filters that may have been applied during model creation.</span></span>  
  
    -   <span data-ttu-id="bab78-131">Wählen Sie die Option **Miningstrukturtestfälle verwenden**aus, um den vollständigen Satz der Testfälle zu verwenden, die als Teil des zurückgehaltenen Datasets der Miningstrukturen definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="bab78-131">Select the option, **Use mining structure test cases**, to use the full set of testing cases that were defined as part of the mining structures holdout data set.</span></span>  
  
    -   <span data-ttu-id="bab78-132">Aktivieren Sie die Option **Anderes Dataset verwenden**, wenn Sie externe Daten verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="bab78-132">Select the option, **Specify a different data set**, if you want to use external data.</span></span>  <span data-ttu-id="bab78-133">Das Dataset muss als Datenquellensicht verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="bab78-133">The data set must be available as a data source view.</span></span>   <span data-ttu-id="bab78-134">Klicken Sie auf die Schaltfläche zum Durchsuchen (**..**.), um die Datentabellen für das Genauigkeits Diagramm auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="bab78-134">Click the browse (**...**) button to choose the data tables to use for the accuracy chart.</span></span> <span data-ttu-id="bab78-135">Weitere Informationen finden Sie unter [Choose and Map Model Testing Data](choose-and-map-model-testing-data.md).</span><span class="sxs-lookup"><span data-stu-id="bab78-135">For more information, see [Choose and Map Model Testing Data](choose-and-map-model-testing-data.md).</span></span>  
  
         <span data-ttu-id="bab78-136">Wenn Sie ein externes Dataset verwenden, können Sie das Eingabedataset optional filtern.</span><span class="sxs-lookup"><span data-stu-id="bab78-136">If you are using an external data set, you can optionally filter the input data set.</span></span> <span data-ttu-id="bab78-137">Weitere Informationen finden Sie unter [Anwenden von Filtern zum Modellieren von Testdaten](apply-filters-to-model-testing-data.md).</span><span class="sxs-lookup"><span data-stu-id="bab78-137">For more information, see [Apply Filters to Model Testing Data](apply-filters-to-model-testing-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bab78-138">Auf der Registerkarte **Eingabeauswahl** können Sie keinen Filter für die Testfälle des Modells oder der Mining Struktur erstellen. Um einen Filter für das Mining Modell zu erstellen, ändern Sie die Filter-Eigenschaft des Modells.</span><span class="sxs-lookup"><span data-stu-id="bab78-138">You cannot create a filter on the model test cases or the mining structure test cases on the **Input Selection** tab. To create a filter on the mining model, modify the Filter property of the model.</span></span> <span data-ttu-id="bab78-139">Weitere Informationen finden Sie unter [Anwenden eines Filters auf ein Miningmodell](apply-a-filter-to-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="bab78-139">For more information, see [Apply a Filter to a Mining Model](apply-a-filter-to-a-mining-model.md).</span></span>  
  
### <a name="configure-chart-settings-and-generate-the-chart"></a><span data-ttu-id="bab78-140">Konfigurieren von Diagrammeinstellungen und Generieren des Diagramms</span><span class="sxs-lookup"><span data-stu-id="bab78-140">Configure chart settings and generate the chart</span></span>  
  
1.  <span data-ttu-id="bab78-141">Klicken Sie in der Registerkarte **Mininggenauigkeitsdiagramm** auf die Registerkarte für das Diagramm, das Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="bab78-141">In the **Mining Accuracy Chart** tab, click the tab for the chart you want to create.</span></span>  
  
2.  <span data-ttu-id="bab78-142">Klicken Sie für ein **Lift Diagramm**auf die Registerkarte **Lift Chart** . Das Diagramm wird automatisch auf Grundlage des Modells, der vorhersagbaren Attribute und der Eingabedaten generiert, die Sie soeben ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="bab78-142">For a **lift chart**, click the **Lift Chart** tab. The chart is automatically generated based on the model, predictable attributes, and input data that you just selected.</span></span>  
  
3.  <span data-ttu-id="bab78-143">Klicken Sie für eine **Klassifikations Matrix**auf die Registerkarte **Klassifikations Matrix** . Es sind keine weiteren Einstellungen erforderlich. das Diagramm wird automatisch auf Grundlage der von Ihnen ausgewählten Eingabedaten und des Modells generiert.</span><span class="sxs-lookup"><span data-stu-id="bab78-143">For a **classification matrix**, click the **Classification Matrix** tab. No further settings are needed; the chart is automatically generated based on the input data and model that you selected.</span></span>  
  
4.  <span data-ttu-id="bab78-144">Klicken Sie für ein **Gewinn Diagramm**zuerst auf die Registerkarte **Lift Chart** . Wählen Sie dann in der Dropdown Liste **Diagrammtyp** die Option **Gewinn Diagramm**aus.</span><span class="sxs-lookup"><span data-stu-id="bab78-144">For a **profit chart**, first click the **Lift Chart** tab. Then, from the **Chart type** drop-down list, select **Profit chart**.</span></span>  
  
     <span data-ttu-id="bab78-145">Geben Sie die folgenden Einstellungen im Dialogfeld **Gewinndiagrammeinstellungen** ein.</span><span class="sxs-lookup"><span data-stu-id="bab78-145">Enter the following settings in the **Profit Chart Settings** dialog box.</span></span>  
  
     <span data-ttu-id="bab78-146">**Bevölkerungs**</span><span class="sxs-lookup"><span data-stu-id="bab78-146">**Population**</span></span>  
     <span data-ttu-id="bab78-147">Die Anzahl von Fällen im Dataset, die Sie beim Erstellen des Prognosegütediagramms verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="bab78-147">The number of cases from the data set that you want to use when creating the lift chart.</span></span>  
  
     <span data-ttu-id="bab78-148">Das Modell wählt die Fälle immer nach sinkender Wahrscheinlichkeit aus. Wenn Sie also potenzielle Kunden bewerten und eine Anzahl auswählen, die der Hälfte der in der Kundendatenbank vorhandenen Kunden entspricht, misst das Modell die Genauigkeit für die Teilmenge der Fälle, die am besten für Ihr Modell geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="bab78-148">The model always chooses the cases in order of decreasing probability; that is, if you are assessing potential customers and you choose a number that represents only half the records in your customer database, the model will measure accuracy on the subset of cases that best fit your model.</span></span>  
  
     <span data-ttu-id="bab78-149">Die Ursache hierfür liegt darin, dass Sie beim Erstellen eines Mailings oder einer Kampagne mit dem Modell die Vorhersagewahrscheinlich für jeden Fall nutzen, um nur die Kunden anzusprechen, die mit höchster Wahrscheinlichkeit einen Kauf tätigen werden.</span><span class="sxs-lookup"><span data-stu-id="bab78-149">This is because when you use the model to generate a mailing or create a campaign, you will use the prediction probability associated with each case to target only the customers who have the highest probability of making a positive response.</span></span>  
  
     <span data-ttu-id="bab78-150">**Festes Kosten**</span><span class="sxs-lookup"><span data-stu-id="bab78-150">**Fixed Cost**</span></span>  
     <span data-ttu-id="bab78-151">Die festen Kosten, die mit dem Geschäftsproblem verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="bab78-151">The fixed cost that is associated with the business problem.</span></span>  
  
     <span data-ttu-id="bab78-152">Bei einer Targeted Mailing-Lösung könnten die festen Kosten beispielsweise die Kosten zum Einrichten eines Druckers umfassen, die die anfänglichen Kosten für die Vorbereitung des Mailings abdecken.</span><span class="sxs-lookup"><span data-stu-id="bab78-152">If this were for a targeted mailing solution, the fixed cost might represent a printer setup fee that covers the initial cost of preparing the promotional mailing.</span></span>  
  
     <span data-ttu-id="bab78-153">Diese Kosten gelten einmal für die gesamte Zielpopulation.</span><span class="sxs-lookup"><span data-stu-id="bab78-153">This cost applies one time to the entire target population.</span></span>  
  
     <span data-ttu-id="bab78-154">**Einzelkosten**</span><span class="sxs-lookup"><span data-stu-id="bab78-154">**Individual Cost**</span></span>  
     <span data-ttu-id="bab78-155">Kosten, die zusätzlich zu den festen Kosten entstehen und den einzelnen Kundenkontakten zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="bab78-155">Costs that are in addition to the fixed cost, that can be associated with each customer contact.</span></span> <span data-ttu-id="bab78-156">Sie könnten beispielsweise die Versandkosten für ein Mailing oder die Kosten für Telefonanrufe eingeben.</span><span class="sxs-lookup"><span data-stu-id="bab78-156">For example, you might enter the postage cost for a promotional mailing or the cost of making telephone calls.</span></span>  
  
     <span data-ttu-id="bab78-157">Diese Kosten müssen für die gesamte Zielpopulation die gleichen sein.</span><span class="sxs-lookup"><span data-stu-id="bab78-157">This cost must be the same for the entire target population.</span></span> <span data-ttu-id="bab78-158">Jeder Wert wird mit der Anzahl der angesprochenen Fälle multipliziert.</span><span class="sxs-lookup"><span data-stu-id="bab78-158">Each value is multiplied by the number of cases that are targeted.</span></span>  
  
     <span data-ttu-id="bab78-159">**Einzelumsatz**</span><span class="sxs-lookup"><span data-stu-id="bab78-159">**Revenue Per Individual**</span></span>  
     <span data-ttu-id="bab78-160">Die Höhe des mit einem erfolgreichen Verkauf verbundenen Umsatzes.</span><span class="sxs-lookup"><span data-stu-id="bab78-160">The amount of revenue that is associated with each successful sale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bab78-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bab78-161">See Also</span></span>  
 <span data-ttu-id="bab78-162">[Lift Chart &#40;Analysis Services-Data Mining-&#41;](lift-chart-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="bab78-162">[Lift Chart &#40;Analysis Services - Data Mining&#41;](lift-chart-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="bab78-163">Klassifikationsmatrix &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="bab78-163">Classification Matrix &#40;Analysis Services - Data Mining&#41;</span></span>](classification-matrix-analysis-services-data-mining.md)  
  
  
