---
title: Assistent zum Schätzen von Daten (Data Mining-Add-Ins für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data modeling [data mining]
- estimation
ms.assetid: 7f2b1d5f-c9b3-4939-b35a-34ae099af15f
author: minewiskan
ms.author: owend
ms.openlocfilehash: ace9fa3a62690061677312d4f7dbb6b8a1d0ea5a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718880"
---
# <a name="estimate-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="1b1bd-102">Assistent zum Schätzen von Daten (Data Mining-Add-Ins für Excel)</span><span class="sxs-lookup"><span data-stu-id="1b1bd-102">Estimate Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="1b1bd-103">![Assistent zum Schätzen von Daten (Data Mining-Menüband)](media/dmc-estimate.gif "Assistent zum Schätzen von Daten (Data Mining-Menüband)")</span><span class="sxs-lookup"><span data-stu-id="1b1bd-103">![Estimate wizard in Data Mining ribbon](media/dmc-estimate.gif "Estimate wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="1b1bd-104">Der Assistent für die **Schätzung** unterstützt Sie beim Erstellen eines Schätz Modells.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-104">The **Estimate** wizard helps you create an estimation model.</span></span> <span data-ttu-id="1b1bd-105">Ein Schätzmodell extrahiert Datenmuster und verwendet diese Muster, um die Faktoren vorherzusagen, die sich auf Ergebnisse auswirken.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-105">An estimation model extracts patterns from data and uses the patterns to predict the factors that affect outcomes.</span></span>  
  
 <span data-ttu-id="1b1bd-106">Die Schätzung wird für die Vorhersage von numerischen Ergebnissen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-106">Estimation is used for predicting numeric outcomes.</span></span> <span data-ttu-id="1b1bd-107">Wenn die Ziel Spalte z. b. die Abschluss Raten für Schulen enthält und die Abschluss Sätze als Prozentsätze ausgedrückt werden, können Sie Faktoren analysieren, die die Abschluss Raten potenziell erhöhen oder verringern, wie z. b. die Anzahl der Schüler/Studenten pro Schule, das Verhältnis des Studenten Lehrers und die Anzahl der Lehrkräfte.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-107">For example, if your target column contains graduation rates for schools, with graduation rates expressed as percentages, you could analyze factors that potentially increase or decrease graduation rates, such as the number of students per school, the student-teacher ratio, and the number of teachers.</span></span>  
  
## <a name="using-the-estimate-data-wizard"></a><span data-ttu-id="1b1bd-108">Verwenden des Assistenten zum Schätzen von Daten</span><span class="sxs-lookup"><span data-stu-id="1b1bd-108">Using the Estimate Data Wizard</span></span>  
  
1.  <span data-ttu-id="1b1bd-109">Klicken Sie im Menüband **Data Mining** auf **Schätzung**.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-109">On the **Data Mining** ribbon, click **Estimate**.</span></span>  
  
2.  <span data-ttu-id="1b1bd-110">Wählen Sie im Dialogfeld **Quelldaten auswählen** die Quelldaten aus, die verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-110">In the **Select Source Data** dialog box, select the source data to use.</span></span> <span data-ttu-id="1b1bd-111">Sie können Daten in einer Excel- **Tabelle**, einem Excel- **Datenbereich**oder einer **externen Datenquelle**verwenden.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-111">You can use data in an Excel **Table**, an Excel **Data Range**, or from an **External data source**.</span></span>  
  
     <span data-ttu-id="1b1bd-112">Wenn Sie eine externe Datenquelle verwenden, können Sie benutzerdefinierte Sichten oder Abfragen erstellen und als [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Datenquelle speichern.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-112">If you use an external data source, you can create custom views or queries and save them as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source.</span></span>  
  
3.  <span data-ttu-id="1b1bd-113">Wählen Sie im Dialogfeld **Schätzung** die **zu analysierende Spalte**aus.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-113">In the **Estimation** dialog box, select the **Column to analyze**.</span></span>  
  
     <span data-ttu-id="1b1bd-114">Die Zielspalte muss kontinuierliche numerische Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-114">The target column must contain continuous numeric data.</span></span>  
  
4.  <span data-ttu-id="1b1bd-115">Wählen Sie die zu verwendenden Spalten aus, indem Sie das Kontrollkästchen **Eingabe Spalten** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-115">Select columns to use as input by checking the **Input columns** checkbox.</span></span>  
  
     <span data-ttu-id="1b1bd-116">Diese Spalten werden zum Erstellen der Muster verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-116">These columns will be used to create the patterns.</span></span> <span data-ttu-id="1b1bd-117">Es empfiehlt sich, alle Spalten aus der Analyse auszuschließen, die voraussichtlich nicht hilfreich bei einer Analyse sind (z. B. ID-Nummern) oder irrelevante Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-117">You should eliminate from analysis any columns that are not likely to help, such as ID numbers, or columns that contain irrelevant data.</span></span>  
  
5.  <span data-ttu-id="1b1bd-118">Der Assistent zum **schätzen** wählt den optimalen Algorithmus für das DataSet aus.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-118">The **Estimate** wizard selects the optimum algorithm for your data set.</span></span> <span data-ttu-id="1b1bd-119">Sie können jedoch auf **Parameter** klicken, um das Dialogfeld **Algorithmusparameter** zu öffnen und erweiterte Optionen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-119">However, you can click **Parameters** to open the **Algorithm Parameters** dialog box and set advanced options.</span></span>  
  
6.  <span data-ttu-id="1b1bd-120">Wenn die Daten numerisch sind und Sie die lineare Regressions Methode von Microsoft verwenden können, können Sie das Feld **Regressor** für alle numerischen Spalten aktivieren, die Sie kennen (oder stark vermuten), die mit dem vorhersagbaren Wert korreliert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-120">If your data is numeric and you can use the Microsoft Linear Regression method, you can check the **Regressor** box for any numeric columns that you know (or strongly suspect) to be correlated with the predictable value.</span></span>  
  
     <span data-ttu-id="1b1bd-121">Der Algorithmus testet dann die Werte in der betreffenden Spalte, um zu ermitteln, ob sie sich auf die Ergebnisse auswirken.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-121">The algorithm will then test the values in that column to determine if they affect the outcomes.</span></span> <span data-ttu-id="1b1bd-122">Wenn Sie sich nicht sicher sind, klicken Sie auf **vorschlagen** , und der Algorithmus testet alle Spalten und erkennt automatisch die besten Werte, die als Regressoren verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-122">If you are unsure, click **Suggest** and the algorithm will test all column and automatically detect the best values to use as regressors.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1b1bd-123">Ein Regressor ist erforderlich, um eine Schätzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-123">A regressor is required to create an estimate.</span></span> <span data-ttu-id="1b1bd-124">Der Assistent empfiehlt auf Grundlage eines ersten Datendurchlaufs immer den besten Regressor.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-124">The wizard always recommends the best regressor, based on an initial pass over the data.</span></span> <span data-ttu-id="1b1bd-125">Wenn Sie nicht sicher sind, ist es deshalb am besten, die empfohlene Auswahl zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-125">Therefore, if you are not sure, it is best to accept the recommended selections.</span></span>  
  
7.  <span data-ttu-id="1b1bd-126">Geben Sie auf der Seite **Daten in Trainings-und Testsätze aufteilen** an, ob Sie eine kleine Teilmenge der Daten für Tests erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-126">On the **Split data into training and testing sets** page, specify whether you want to create a small subset of the data for testing.</span></span>  
  
8.  <span data-ttu-id="1b1bd-127">Geben Sie auf der Seite **Fertig** stellen Namen für die neue Mining Struktur und den Mining Modus an, oder übernehmen Sie die bereitgestellten Standardnamen.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-127">On the **Finish** page, provide names for the new mining structure and mining mode, or accept the default names that are provided.</span></span>  
  
9. <span data-ttu-id="1b1bd-128">Legen Sie die Optionen zum Verwenden des Modells fest.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-128">Set options for using the model.</span></span>  
  
    -   <span data-ttu-id="1b1bd-129">Wählen Sie **Durchsuchen** aus, um das Modell direkt in einem Viewer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-129">Select **Browse** to immediately open the model in a viewer.</span></span>  
  
         <span data-ttu-id="1b1bd-130">Dieser grafische Viewer zeigt ein Abhängigkeitsnetzwerkdiagramm und die vom Algorithmus generierte Entscheidungsstruktur an.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-130">This graphical viewer displays a dependency network graph and the decision tree generated by the algorithm.</span></span> <span data-ttu-id="1b1bd-131">Untersuchen Sie diese Informationen, um sich ein Bild von den Faktoren zu machen, die die geschätzten Werte beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-131">By exploring this information, you can better understand the factors that contribute to the estimated values.</span></span>  
  
    -   <span data-ttu-id="1b1bd-132">Wählen Sie **Drillthrough aktivieren** aus, damit Benutzer Ihrer Analyse die zugrunde liegenden Daten anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-132">Select **Enable drillthrough** to let users of your analysis view the underlying data.</span></span>  
  
         <span data-ttu-id="1b1bd-133">Diese Option ist nur verfügbar, wenn Sie den Decision Trees-Algorithmus oder den Linear Regression-Algorithmus verwenden.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-133">This option is available only if you use the Decision Trees opr Linear Regression algorithms.</span></span>  
  
    -   <span data-ttu-id="1b1bd-134">**Temporäres Modell verwenden**.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-134">**Use temporary model**.</span></span> <span data-ttu-id="1b1bd-135">Wenn Sie diese Option auswählen, wird das Modell nicht auf dem Server gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-135">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="1b1bd-136">Temporäre Modelle werden beim Schließen von Excel gelöscht.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-136">Temporary models are deleted when you close Excel.</span></span>  
  
## <a name="more-about-estimation-models"></a><span data-ttu-id="1b1bd-137">Weitere Informationen zu Schätzmodellen</span><span class="sxs-lookup"><span data-stu-id="1b1bd-137">More About Estimation Models</span></span>  
 <span data-ttu-id="1b1bd-138">Der Assistent für die **Schätzung** unterstützt die Verwendung der folgenden Algorithmen:</span><span class="sxs-lookup"><span data-stu-id="1b1bd-138">The **Estimate** wizard supports the use of any of the following algorithms:</span></span>  
  
-   <span data-ttu-id="1b1bd-139">Microsoft Decision Tree-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="1b1bd-139">Microsoft Decision Tree algorithm</span></span>  
  
-   <span data-ttu-id="1b1bd-140">Microsoft Linear Regression-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="1b1bd-140">Microsoft Linear Regression algorithm</span></span>  
  
-   <span data-ttu-id="1b1bd-141">Microsoft Logistic Regression-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="1b1bd-141">Microsoft Logistic Regression algorithm</span></span>  
  
-   <span data-ttu-id="1b1bd-142">Microsoft Neural Network-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="1b1bd-142">Microsoft Neural network algorithm</span></span>  
  
 <span data-ttu-id="1b1bd-143">Im Dialogfeld **Algorithmusparameter** können Sie je nach ausgewähltem Algorithmus zusätzliche erweiterte Optionen festlegen.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-143">In the **Algorithm Parameters** dialog box, you can set additional advanced options, depending on which algorithm you chose.</span></span> <span data-ttu-id="1b1bd-144">Weitere Informationen zu den Optionen für die einzelnen Algorithmen finden Sie in der SQL Server-Onlinedokumentation in folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1b1bd-144">For information on the options for each algorithm see these topics in SQL Server Books Online:</span></span>  
  
 [<span data-ttu-id="1b1bd-145">Technische Referenz für den Microsoft Decision Trees-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="1b1bd-145">Microsoft Decision Trees Algorithm Technical Reference</span></span>](data-mining/microsoft-decision-trees-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="1b1bd-146">Technische Referenz für den Microsoft Linear Regression-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="1b1bd-146">Microsoft Linear Regression Algorithm Technical Reference</span></span>](data-mining/microsoft-linear-regression-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="1b1bd-147">Technische Referenz für den Microsoft Logistic Regression-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="1b1bd-147">Microsoft Logistic Regression Algorithm Technical Reference</span></span>](data-mining/microsoft-logistic-regression-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="1b1bd-148">Technische Referenz für den Microsoft Neural Network-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="1b1bd-148">Microsoft Neural Network Algorithm Technical Reference</span></span>](data-mining/microsoft-neural-network-algorithm-technical-reference.md)  
  
### <a name="requirements"></a><span data-ttu-id="1b1bd-149">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1b1bd-149">Requirements</span></span>  
 <span data-ttu-id="1b1bd-150">Zum Verwenden des Assistenten zum Schätzen von Daten muss eine Verbindung mit einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Datenbank bestehen.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-150">To use the Estimate Data Wizard, you must be connected to a [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="1b1bd-151">Weitere Informationen zum Erstellen einer Verbindung finden Sie unter Herstellen einer Verbindung [mit Quelldaten &#40;Data Mining-Client für Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="1b1bd-151">For information about how to create a connection, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
 <span data-ttu-id="1b1bd-152">Um den Schätzalgorithmus zu verwenden, muss das Ergebnis, das vorhergesagt werden soll, als numerischer Wert ausgedrückt werden, z. B. als Währung, Umsatz, Datum oder Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="1b1bd-152">To use the estimation algorithm, the outcome that you are trying to predict must be expressed as a numeric value, such as a currency, sales amount, date, or time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b1bd-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b1bd-153">See Also</span></span>  
 <span data-ttu-id="1b1bd-154">[Erstellen eines Data Mining-Modells](creating-a-data-mining-model.md) </span><span class="sxs-lookup"><span data-stu-id="1b1bd-154">[Creating a Data Mining Model](creating-a-data-mining-model.md) </span></span>  
 [<span data-ttu-id="1b1bd-155">Entscheidungsstruktur Diagramm Exemplarische Vorgehensweise &#40;Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="1b1bd-155">Decision Tree Diagram Walkthrough  &#40;Data Mining Add-ins&#41;</span></span>](decision-tree-diagram-walkthrough-data-mining-add-ins.md)  
  
  
