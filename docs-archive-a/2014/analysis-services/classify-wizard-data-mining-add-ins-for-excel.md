---
title: Assistent zum Klassifizieren (Data Mining-Add-Ins für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data modeling [data mining]
- classification [data mining]
ms.assetid: 409c5076-c4c3-4f09-8f30-d3297df45f13
author: minewiskan
ms.author: owend
ms.openlocfilehash: b82fc98df10ae2e6754a378dacea108f9f3379ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610272"
---
# <a name="classify-wizard-data-mining-add-ins-for-excel"></a><span data-ttu-id="a161a-102">Assistent zum Klassifizieren (Data Mining-Add-Ins für Excel)</span><span class="sxs-lookup"><span data-stu-id="a161a-102">Classify Wizard (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="a161a-103">![Assistent zum Klassifizieren (Data Mining-Menüband)](media/dmc-classify.gif "Assistent zum Klassifizieren (Data Mining-Menüband)")</span><span class="sxs-lookup"><span data-stu-id="a161a-103">![Classify wizard in Data Mining ribbon](media/dmc-classify.gif "Classify wizard in Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="a161a-104">Der Assistent zum **klassifizieren** unterstützt Sie beim Erstellen eines Klassifizierungs Modells auf der Grundlage vorhandener Daten in einer Excel-Tabelle, eines Excel-Bereichs oder einer externen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="a161a-104">The **Classify** wizard helps you build a classification model based on existing data in an Excel table, an Excel range, or an external data source.</span></span>  
  
 <span data-ttu-id="a161a-105">Mit einem Klassifizierungsmodell werden Muster in den Daten extrahiert, die auf Übereinstimmungen hinweisen. So können Sie Vorhersagen basierend auf Wertgruppen treffen.</span><span class="sxs-lookup"><span data-stu-id="a161a-105">A classification model extracts patterns in your data that indicate similarities and helps you make predictions based on groupings of values.</span></span> <span data-ttu-id="a161a-106">Ein Klassifizierungsmodell kann beispielsweise verwendet werden, um das Risiko auf der Grundlage von Einkommens- und Konsummustern vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="a161a-106">For example, a classification model might be used to predict risk based on income or spending patterns.</span></span>  
  
## <a name="using-the-classify-wizard"></a><span data-ttu-id="a161a-107">Verwenden des Assistenten zum Klassifizieren</span><span class="sxs-lookup"><span data-stu-id="a161a-107">Using the Classify Wizard</span></span>  
  
1.  <span data-ttu-id="a161a-108">Klicken Sie im Menüband **Data Mining** auf **klassifizieren**und dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a161a-108">In the **Data Mining** ribbon, click **Classify**, and then click **Next**.</span></span>  
  
2.  <span data-ttu-id="a161a-109">Wählen Sie auf der Seite **Quelldaten auswählen** die zu analysierenden Daten aus.</span><span class="sxs-lookup"><span data-stu-id="a161a-109">In the **Select Source Data** page, choose the data to analyze.</span></span>  
  
     <span data-ttu-id="a161a-110">Dieser Assistent unterstützt verschiedene Daten: Excel-Tabellen, Excel-Bereiche und externe Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="a161a-110">This wizard supports multiple kinds of data: Excel tables, Excel ranges, and external data sources.</span></span> <span data-ttu-id="a161a-111">Externe Daten können Sie entweder zu Excel hinzufügen, oder Sie wählen in einer Analysis Services-Datenquelle eine Gruppe von Tabellen oder Sichten aus.</span><span class="sxs-lookup"><span data-stu-id="a161a-111">With external data, you can either add it into Excel, or choose a set of tables or views in an Analysis Services data source.</span></span> <span data-ttu-id="a161a-112">Sie können auch Tabellen hinzufügen und Spalten ändern, um Ad-hoc-Datenquellen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a161a-112">You can also add tables and change columns to create ad hoc data sources.</span></span>  
  
3.  <span data-ttu-id="a161a-113">Wählen Sie auf der Seite **Klassifizierung** die Spalte aus, die Sie klassifizieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a161a-113">On the **Classification** page, choose the column that you want to classify.</span></span>  
  
     <span data-ttu-id="a161a-114">Überprüfen Sie die Spalten in der Liste, **Eingabe Spalten**, und deaktivieren Sie alle Spalten, die eindeutige Werte aufweisen und daher nicht zum Erstellen von Mustern wie ID-Nummern, Kundennamen usw. nützlich sind.</span><span class="sxs-lookup"><span data-stu-id="a161a-114">Review the columns in the list, **Input columns**, and deselect any columns that have unique values and thus aren't useful for creating patterns, such as ID numbers, customer names, and so on.</span></span> <span data-ttu-id="a161a-115">Außerdem sollten Sie auch die Spalten entfernen, die die klassifizierbare Spalte im Grunde duplizieren.</span><span class="sxs-lookup"><span data-stu-id="a161a-115">You should also remove columns that essentially duplicate the classifiable column.</span></span>  
  
     <span data-ttu-id="a161a-116">Wenn Sie zum Beispiel die Kategorieprognose eines Produkts klassifizieren, sollten Sie das Feld mit der Unterkategorie ausschließen, wenn eine bekannte Geschäftsregel vorhanden ist. Andernfalls könnte die Stärke dieser Regel verhindern, dass Sie andere Korrelationen erkennen.</span><span class="sxs-lookup"><span data-stu-id="a161a-116">For example, if you are classifying predicting the category of a product, you should exclude the subcategory field if there is a known business rule, or else the strength of that rule might prevent you from discovering other correlations.</span></span>  
  
4.  <span data-ttu-id="a161a-117">Klicken Sie optional auf **Parameter** , um die Algorithmusparameter zu ändern und das Verhalten des Clustering-Modells anzupassen.</span><span class="sxs-lookup"><span data-stu-id="a161a-117">Optionally, click **Parameters** to change the algorithm parameters and customize the behavior of the clustering model.</span></span>  
  
5.  <span data-ttu-id="a161a-118">Geben Sie auf der Seite **Daten in Trainings-und Testsätze aufteilen** an, wie viele Daten zum Testen aufbewahrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a161a-118">In the **Split data into training and testing sets** page, specify how much data to hold out for testing.</span></span> <span data-ttu-id="a161a-119">Der Rest wird immer zum Trainieren des Modells verwendet.</span><span class="sxs-lookup"><span data-stu-id="a161a-119">The remainder is always used for training the model.</span></span>  
  
     <span data-ttu-id="a161a-120">In der Standardeinstellung sind 30 % als Testdaten und 70 % als Trainingsdaten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a161a-120">The default setting is 30% testing data and 70% training data.</span></span>  
  
6.  <span data-ttu-id="a161a-121">Geben Sie auf der Seite **Fertig** stellen einen beschreibenden Namen für das DataSet und das Modell an, und legen Sie die folgenden Optionen fest, mit denen die Arbeit mit dem fertigen Modell gesteuert wird:</span><span class="sxs-lookup"><span data-stu-id="a161a-121">On the **Finish** page, provide a descriptive name for your data set and model, and set the following options that control how you work with the finished model:</span></span>  
  
    -   <span data-ttu-id="a161a-122">**Modell durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="a161a-122">**Browse model**.</span></span> <span data-ttu-id="a161a-123">Wenn diese Option ausgewählt ist, wird das Fenster **Durchsuchen** geöffnet, sobald der Assistent die Verarbeitung des Modells abgeschlossen hat, damit Sie die Ergebnisse untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="a161a-123">When this option is selected, as soon as the wizard finishes processing the model, it opens a **Browse** window to help you explore the results.</span></span> <span data-ttu-id="a161a-124">Der Inhalt des Viewers hängt vom Typ des erstellten Modells ab.</span><span class="sxs-lookup"><span data-stu-id="a161a-124">The contents of the viewer depend on the type of model you built.</span></span> <span data-ttu-id="a161a-125">Weitere Informationen finden Sie unter durch [Suchen eines Entscheidungsstruktur Modells](browsing-a-decision-trees-model.md) und durch [Suchen eines neuronalen Netzwerk Modells](browsing-a-neural-network-model.md).</span><span class="sxs-lookup"><span data-stu-id="a161a-125">For more information, see [Browsing a Decision Trees Model](browsing-a-decision-trees-model.md) and [Browsing a Neural Network Model](browsing-a-neural-network-model.md).</span></span>  
  
    -   <span data-ttu-id="a161a-126">**Drillthrough aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="a161a-126">**Enable drillthrough**.</span></span> <span data-ttu-id="a161a-127">Wählen Sie diese Option aus, um die zugrunde liegenden Daten des fertigen Modells anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a161a-127">Select this option to view the underlying data from the finished model.</span></span> <span data-ttu-id="a161a-128">Diese Option ist nur verfügbar, wenn Sie ein Decision Tree-Modell erstellen.</span><span class="sxs-lookup"><span data-stu-id="a161a-128">This option is only available if you build a Decision Tree model.</span></span>  
  
    -   <span data-ttu-id="a161a-129">**Temporäres Modell verwenden**.</span><span class="sxs-lookup"><span data-stu-id="a161a-129">**Use temporary model**.</span></span> <span data-ttu-id="a161a-130">Wenn Sie diese Option auswählen, wird das Modell nicht auf dem Server gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a161a-130">If you select this option, the model will not be saved to the server.</span></span> <span data-ttu-id="a161a-131">Temporäre Modelle werden beim Schließen von Excel gelöscht.</span><span class="sxs-lookup"><span data-stu-id="a161a-131">Temporary models are deleted when you close Excel.</span></span>  
  
## <a name="more-about-classification-models"></a><span data-ttu-id="a161a-132">Weitere Informationen zu Klassifikationsmodellen</span><span class="sxs-lookup"><span data-stu-id="a161a-132">More About Classification Models</span></span>  
 <span data-ttu-id="a161a-133">Im Dialogfeld **Algorithmusparameter** können Sie auch die Klassifizierungsmethode aus diesen Algorithmen auswählen, die in Analysis Services bereitgestellt werden:</span><span class="sxs-lookup"><span data-stu-id="a161a-133">In the **Algorithm Parameters** dialog box, you can also choose the classification method from among these algorithms provided in Analysis Services:</span></span>  
  
-   <span data-ttu-id="a161a-134">Microsoft Decision Tree</span><span class="sxs-lookup"><span data-stu-id="a161a-134">Microsoft Decision Tree</span></span>  
  
-   <span data-ttu-id="a161a-135">Microsoft Logistic Regression</span><span class="sxs-lookup"><span data-stu-id="a161a-135">Microsoft Logistic Regression</span></span>  
  
-   <span data-ttu-id="a161a-136">Microsoft Naive Bayes</span><span class="sxs-lookup"><span data-stu-id="a161a-136">Microsoft Naïve Bayes</span></span>  
  
-   <span data-ttu-id="a161a-137">Microsoft Neural Network</span><span class="sxs-lookup"><span data-stu-id="a161a-137">Microsoft Neural Network</span></span>  
  
 <span data-ttu-id="a161a-138">Die Algorithmen führen zwar zu ähnlichen Ergebnissen, doch die Daten werden unterschiedlich analysiert. Daher wird empfohlen, mehrere Algorithmen zu testen und die Ergebnisse zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="a161a-138">Although the algorithms might yield similar results, they analyze the data differently, so we recommend trying several algorithms and comparing the results.</span></span> <span data-ttu-id="a161a-139">Die Standardmethode ist Microsoft Decision Trees.</span><span class="sxs-lookup"><span data-stu-id="a161a-139">The default method is Microsoft Decision Trees.</span></span>  
  
 <span data-ttu-id="a161a-140">In der Liste **Parameter** können Sie erweiterte Optionen ändern, die vom gewählten Algorithmustyp abhängen.</span><span class="sxs-lookup"><span data-stu-id="a161a-140">In the **Parameters** list, you can change advanced options, which depend on the type of algorithm you choose.</span></span> <span data-ttu-id="a161a-141">Die Parameter für die einzelnen Algorithmen werden in der SQL Server-Onlinedokumentation ausführlicher beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a161a-141">The parameters for each algorithm are described in more detail in SQL Server Books Online.</span></span>  
  
 [<span data-ttu-id="a161a-142">Technische Referenz für den Microsoft Decision Trees-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="a161a-142">Microsoft Decision Trees Algorithm Technical Reference</span></span>](data-mining/microsoft-decision-trees-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="a161a-143">Technische Referenz für den Microsoft Logistic Regression-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="a161a-143">Microsoft Logistic Regression Algorithm Technical Reference</span></span>](data-mining/microsoft-logistic-regression-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="a161a-144">Technische Referenz für den Microsoft Naive Bayes-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="a161a-144">Microsoft Naive Bayes Algorithm Technical Reference</span></span>](data-mining/microsoft-naive-bayes-algorithm-technical-reference.md)  
  
 [<span data-ttu-id="a161a-145">Technische Referenz für den Microsoft Neural Network-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="a161a-145">Microsoft Neural Network Algorithm Technical Reference</span></span>](data-mining/microsoft-neural-network-algorithm-technical-reference.md)  
  
### <a name="requirements"></a><span data-ttu-id="a161a-146">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a161a-146">Requirements</span></span>  
 <span data-ttu-id="a161a-147">Wenn Sie den **klassifizier** enden Assistenten verwenden möchten, müssen Sie mit einer-Datenbank verbunden sein [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a161a-147">To use the **Classify** wizard, you must be connected to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="a161a-148">Weitere Informationen zum Erstellen einer Verbindung finden Sie unter Herstellen einer Verbindung [mit Quelldaten &#40;Data Mining-Client für Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="a161a-148">For information about how to create a connection, see [Connect to Source Data &#40;Data Mining Client for Excel&#41;](connect-to-source-data-data-mining-client-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a161a-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a161a-149">See Also</span></span>  
 [<span data-ttu-id="a161a-150">Erstellen eines Data Mining-Modells</span><span class="sxs-lookup"><span data-stu-id="a161a-150">Creating a Data Mining Model</span></span>](creating-a-data-mining-model.md)  
  
  
