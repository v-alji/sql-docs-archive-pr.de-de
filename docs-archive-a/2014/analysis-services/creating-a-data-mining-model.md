---
title: Erstellen eines Data Mining-Modells | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data mining models, creating
- forecasting [data mining]
- mining models, creating
- clustering [data mining]
- association [data mining]
- data modeling [data mining]
- estimation
- classification [data mining]
ms.assetid: 804b7db3-1f6a-4f73-a81d-bbe02520d7c6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1e27739d3733c0b48dc6cff3e83e01f9cb12bce7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618944"
---
# <a name="creating-a-data-mining-model"></a><span data-ttu-id="4174e-102">Erstellen eines Data Mining-Modells</span><span class="sxs-lookup"><span data-stu-id="4174e-102">Creating a Data Mining Model</span></span>
  <span data-ttu-id="4174e-103">Die Datenmodellierung ist der Schritt der Data Mining, in dem Sie Muster und Trends durch Anwenden von *Algorithmen* auf Daten erstellen.</span><span class="sxs-lookup"><span data-stu-id="4174e-103">Data modeling is the step of data mining where you build patterns and trends by applying *algorithms* to data.</span></span> <span data-ttu-id="4174e-104">Später können Sie anhand dieser Muster Analysen ausführen oder Vorhersagen treffen.</span><span class="sxs-lookup"><span data-stu-id="4174e-104">Later you can use those patterns for analysis, or to make predictions.</span></span>  
  
 <span data-ttu-id="4174e-105">Die Data Mining-Add-Ins für Office unterstützen das Data Mining über Assistenten, die das Erstellen von Modellen erleichtern.</span><span class="sxs-lookup"><span data-stu-id="4174e-105">The Data Mining Add-ins for Office support data mining through wizards that make it easy to create models.</span></span> <span data-ttu-id="4174e-106">Mit den Assistenten werden Daten analysiert und Korrelationen identifiziert sowie die statistische Bedeutung aller Variablen berechnet und automatisch das beste Modell ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="4174e-106">The wizards analyze the data, identify correlations, compute statistical significance of all variables, and automatically select the best model.</span></span>  
  
 <span data-ttu-id="4174e-107">Obwohl diese Funktionalität jedes wenig leistungsfähig ist, wie die Data Mining Tools von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] und [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] , erleichtert die Kombination von Assistenten und der vertrauten Excel-Oberfläche die Erstellung, Änderung und Verwendung von Data Mining.</span><span class="sxs-lookup"><span data-stu-id="4174e-107">Although this functionality is every bit as powerful as the data mining tools provided by [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], the combination of wizards and the familiar Excel interface makes it easy to create, modify, and use data mining.</span></span>  
  
## <a name="advanced-data-mining"></a><span data-ttu-id="4174e-108">Erweitert (Data Mining)</span><span class="sxs-lookup"><span data-stu-id="4174e-108">Advanced (Data Mining)</span></span>  
 <span data-ttu-id="4174e-109">Mit den erweiterten Assistenten können Sie neue Data Mining Modelle basierend auf in Excel gespeicherten Daten erstellen, indem Sie einen der Data Mining Algorithmen in verwenden [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4174e-109">The Advanced wizards let you create new data mining models, based on data stored in Excel, by using one of the data mining algorithms in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
### <a name="create-mining-structure"></a><span data-ttu-id="4174e-110">Erstellen einer Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="4174e-110">Create Mining Structure</span></span>  
 <span data-ttu-id="4174e-111">Der Strukturerstellungs-Assistent unterstützt Sie beim Erstellen einer neuen Data Mining-Struktur, die Sie als Grundlage für mehrere Miningmodelle verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4174e-111">The Create Mining Structure wizard helps you build a new data mining structure, which you can use as the basis for multiple mining models.</span></span> <span data-ttu-id="4174e-112">Der Assistent bietet die Option, einen Teil der Daten für ein Testset zu reservieren. So können alle Modelle geschätzt werden, die dieselben Daten nach einem gleich bleibenden Teststandard verwenden.</span><span class="sxs-lookup"><span data-stu-id="4174e-112">The wizard gives you the option to set aside a portion of the data to use as a testing set, so that you can evaluate all models that use the same data according to a consistent testing standard.</span></span>  
  
 [<span data-ttu-id="4174e-113">Mining Struktur &#40;SQL Server Data Mining-Add-Ins erstellen&#41;</span><span class="sxs-lookup"><span data-stu-id="4174e-113">Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;</span></span>](create-mining-structure-sql-server-data-mining-add-ins.md)  
  
### <a name="add-model-to-structure"></a><span data-ttu-id="4174e-114">Hinzufügen eines Modells zu einer Struktur</span><span class="sxs-lookup"><span data-stu-id="4174e-114">Add Model to Structure</span></span>  
 <span data-ttu-id="4174e-115">Der Assistent zum Hinzufügen eines Modells zu einer Struktur unterstützt Sie beim Auswählen einer vorhandenen Data Mining-Struktur und Erstellen eines neuen Data Mining-Modells für diese Struktur.</span><span class="sxs-lookup"><span data-stu-id="4174e-115">The Add Model to Structure wizard lets you choose an existing data mining structure and create a new data mining model for it.</span></span> <span data-ttu-id="4174e-116">Sie können mehrere Miningmodelle zu einer Struktur hinzufügen, wobei die Parameter geändert oder verschiedene Data Mining-Algorithmen ausgewählt werden und das Ergebnis angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="4174e-116">You can add multiple mining models to a structure, changing the parameters or choosing different data mining algorithms, and customize the output.</span></span>  
  
 [<span data-ttu-id="4174e-117">Hinzufügen eines Modells zu einer Struktur &#40;Data Mining-Add-Ins für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4174e-117">Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;</span></span>](add-model-to-structure-data-mining-add-ins-for-excel.md)  
  
## <a name="analyze-key-influencers-analyze"></a><span data-ttu-id="4174e-118">Wichtige Einflussfaktoren analysieren (Analysieren)</span><span class="sxs-lookup"><span data-stu-id="4174e-118">Analyze Key Influencers (Analyze)</span></span>  
 <span data-ttu-id="4174e-119">Sie wählen eine Spalte oder einen Ausgabewert von Interesse aus. Anschließend analysiert der Algorithmus alle Eingabedaten, um die Faktoren zu identifizieren, die den größten Einfluss auf das Ziel haben.</span><span class="sxs-lookup"><span data-stu-id="4174e-119">You choose a column or output value of interest, and then the algorithm analyzes all the input data to identify the factors that have the most influence on the target.</span></span> <span data-ttu-id="4174e-120">Optional können Sie einen Bericht erstellen, in dem zwei beliebige Werte miteinander verglichen werden, sodass Sie feststellen können, wie sich die Einflussfaktoren ändern.</span><span class="sxs-lookup"><span data-stu-id="4174e-120">Optionally, you can create a report that compares any two values, so that you can see how the influencers change.</span></span>  
  
 <span data-ttu-id="4174e-121">Das Tool **wichtige Einflussfaktoren analysieren** verwendet den Microsoft Naive Bayes-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="4174e-121">The **Analyze Key Influencers** tool uses the Microsoft Naïve Bayes algorithm.</span></span>  
  
 [<span data-ttu-id="4174e-122">Wichtige Einflussfaktoren &#40;Tabellenanalyse Tools für Excel analysieren&#41;</span><span class="sxs-lookup"><span data-stu-id="4174e-122">Analyze Key Influencers &#40;Table Analysis Tools for Excel&#41;</span></span>](analyze-key-influencers-table-analysis-tools-for-excel.md)  
  
## <a name="associate-data-mining"></a><span data-ttu-id="4174e-123">Zuordnung [Data Mining]</span><span class="sxs-lookup"><span data-stu-id="4174e-123">Associate (Data Mining)</span></span>  
 <span data-ttu-id="4174e-124">Der Zuordnungs-Assistent erstellt ein Zuordnungs Modell, das Zuordnungen zwischen Elementen erkennt **, die in** mehreren Transaktionen angezeigt werden, z. b. in Market Basket-Analysen.</span><span class="sxs-lookup"><span data-stu-id="4174e-124">The **Associate** wizard builds an association model that detects associations between items that appear in multiple transactions: for example, in market basket analysis.</span></span>  
  
 [<span data-ttu-id="4174e-125">Assistenten &#40;Data Mining-Client für Excel zuordnen&#41;</span><span class="sxs-lookup"><span data-stu-id="4174e-125">Associate Wizard &#40;Data Mining Client for Excel&#41;</span></span>](associate-wizard-data-mining-client-for-excel.md)  
  
## <a name="classify-data-mining"></a><span data-ttu-id="4174e-126">Klassifizieren (Data Mining)</span><span class="sxs-lookup"><span data-stu-id="4174e-126">Classify (Data Mining)</span></span>  
 <span data-ttu-id="4174e-127">Der Assistent zum **klassifizieren** erstellt ein Klassifizierungs Modell, das die Faktoren analysiert, die zu einem Zielergebnis beigetragen haben.</span><span class="sxs-lookup"><span data-stu-id="4174e-127">The  **Classify** wizard builds a classification model that analyzes the factors that contributed to a target outcome.</span></span> <span data-ttu-id="4174e-128">Mit diesem Assistenten können mehrere Algorithmen verwendet werden, u. a. Decision Trees, Naive Bayes und Neural Networks.</span><span class="sxs-lookup"><span data-stu-id="4174e-128">You can use multiple algorithms with this wizard, including Decision Trees, Naïve Bayes, and Neural Networks.</span></span>  
  
 [<span data-ttu-id="4174e-129">Assistent zum Klassifizieren &#40;Data Mining-Add-Ins für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4174e-129">Classify Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](classify-wizard-data-mining-add-ins-for-excel.md)  
  
## <a name="cluster-data-mining"></a><span data-ttu-id="4174e-130">Cluster (Data Mining)</span><span class="sxs-lookup"><span data-stu-id="4174e-130">Cluster (Data Mining)</span></span>  
 <span data-ttu-id="4174e-131">Der **Cluster** -Assistent erstellt ein Clusteringmodell, das Gruppen von Zeilen erkennt, die ähnliche Merkmale aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4174e-131">The **Cluster** wizard builds a clustering model that detects groups of rows that share similar characteristics.</span></span> <span data-ttu-id="4174e-132">Clustering (manchmal auch *Segmentierung*genannt) ist eine nicht überwachte Lerntechnik, die sehr nützlich ist, wenn Sie versuchen, Muster und Gruppierungen in neuen Daten zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="4174e-132">Clustering (sometimes called *segmentation*) is an unsupervised learning technique that is very useful when trying to understand patterns and groupings in new data.</span></span>  
  
 <span data-ttu-id="4174e-133">Der Microsoft Clustering-Algorithmus unterstützt diverse Ausführungen des K-Means- und EM (Expectation Maximization)-Clustering.</span><span class="sxs-lookup"><span data-stu-id="4174e-133">The Microsoft Clustering algorithm supports several varieties of both K-means and Expectation maximization (EM) clustering</span></span>  
  
 <span data-ttu-id="4174e-134">Der [Cluster-Assistent &#40;Data Mining-Add-Ins für Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="4174e-134">[Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;](cluster-wizard-data-mining-add-ins-for-excel.md).</span></span>  
  
## <a name="detect-categories-analyze"></a><span data-ttu-id="4174e-135">Kategorien erkennen (Analysieren)</span><span class="sxs-lookup"><span data-stu-id="4174e-135">Detect Categories (Analyze)</span></span>  
 <span data-ttu-id="4174e-136">Mit dem Tool **Kategorien erkennen** können Sie ein beliebiges DataSet hinzufügen und das Clustering anwenden, um Gruppierungen von Daten zu suchen.</span><span class="sxs-lookup"><span data-stu-id="4174e-136">The **Detect Categories** tool lets you add any data set and apply clustering to find groupings of data.</span></span> <span data-ttu-id="4174e-137">Es ist nützlich, um Ähnlichkeiten zu suchen und Gruppen zu erstellen, um Sie weiter zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="4174e-137">It's useful for finding similarities and for creating groups to further analyze.</span></span>  
  
 <span data-ttu-id="4174e-138">Das Tool **Kategorien erkennen** verwendet den Microsoft Clustering-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="4174e-138">The **Detect Categories** tool uses the Microsoft Clustering algorithm.</span></span>  
  
 [<span data-ttu-id="4174e-139">Erkennen von Kategorien &#40;Tabellenanalyse Tools für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4174e-139">Detect Categories &#40;Table Analysis Tools for Excel&#41;</span></span>](detect-categories-table-analysis-tools-for-excel.md)  
  
## <a name="estimate-data-mining"></a><span data-ttu-id="4174e-140">Schätzung (Data Mining)</span><span class="sxs-lookup"><span data-stu-id="4174e-140">Estimate (Data Mining)</span></span>  
 <span data-ttu-id="4174e-141">Der Assistent zum Schätzen von Daten erstellt ein Schätzmodell, von dem Datenmuster extrahiert und die Muster verwendet werden, um kontinuierliche numerische Werte, Datums- oder Zeitwerte vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="4174e-141">The Estimate wizard builds an estimation model that extracts data patterns and uses the patterns to predict continuous numeric, date, or time values.</span></span> <span data-ttu-id="4174e-142">Er verwendet den [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="4174e-142">It uses the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span>  
  
 [<span data-ttu-id="4174e-143">Assistent zum Schätzen von Daten &#40;Data Mining-Add-Ins für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4174e-143">Estimate Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](estimate-wizard-data-mining-add-ins-for-excel.md)  
  
## <a name="fill-from-example-analyze"></a><span data-ttu-id="4174e-144">Aus Beispiel füllen (Analysieren)</span><span class="sxs-lookup"><span data-stu-id="4174e-144">Fill From Example (Analyze)</span></span>  
 <span data-ttu-id="4174e-145">Mit dem Tool **aus Beispiel füllen** können Sie fehlende Werte angeben.</span><span class="sxs-lookup"><span data-stu-id="4174e-145">The **Fill From Example** tool helps you impute missing values.</span></span> <span data-ttu-id="4174e-146">Sie geben einige Beispiele dafür an, worum es sich bei den fehlenden Werten handeln soll, und das Tool erstellt anhand sämtlicher Daten in der Tabelle Muster. Anschließend werden auf der Grundlage der Muster in den Daten neue Werte empfohlen.</span><span class="sxs-lookup"><span data-stu-id="4174e-146">You provide some examples of what the missing values should be, and the tool builds patterns based on all data in the table, and then recommends new values based on patterns in the data.</span></span>  
  
 <span data-ttu-id="4174e-147">Das Tool **aus Beispiel füllen** verwendet den Microsoft Logistic Regression-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="4174e-147">The **Fill From Example** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 [<span data-ttu-id="4174e-148">Füllen Sie aus Beispiel &#40;Tabellenanalyse Tools für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4174e-148">Fill From Example &#40;Table Analysis Tools for Excel&#41;</span></span>](fill-from-example-table-analysis-tools-for-excel.md)  
  
## <a name="forecast-analyze"></a><span data-ttu-id="4174e-149">Planung (Analysieren)</span><span class="sxs-lookup"><span data-stu-id="4174e-149">Forecast (Analyze)</span></span>  
 <span data-ttu-id="4174e-150">Das Tool für die **Vorhersage** nimmt Daten, die sich im Laufe der Zeit ändern, und prognostiziert zukünftige Werte.</span><span class="sxs-lookup"><span data-stu-id="4174e-150">The **Forecast** tool takes data that changes over time, and predicts future values.</span></span>  
  
 <span data-ttu-id="4174e-151">Das Tool für die **Vorhersage** verwendet den Microsoft Time Series-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="4174e-151">The **Forecast** tool uses the Microsoft Time Series algorithm.</span></span>  
  
 [<span data-ttu-id="4174e-152">Vorhersage &#40;Tabellenanalyse Tools für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4174e-152">Forecast &#40;Table Analysis Tools for Excel&#41;</span></span>](forecast-table-analysis-tools-for-excel.md)  
  
## <a name="forecast-data-mining"></a><span data-ttu-id="4174e-153">Planung [Data Mining]</span><span class="sxs-lookup"><span data-stu-id="4174e-153">Forecast (Data Mining)</span></span>  
 <span data-ttu-id="4174e-154">Der **Planungs** -Assistent erstellt ein Planungsmodell, das Muster in einer Reihe von Zellen erkennt und anschließend weitere Werte vorhersagt.</span><span class="sxs-lookup"><span data-stu-id="4174e-154">The **Forecast** wizard builds a forecasting model that detects patterns in a series of cells, and then forecasts additional values.</span></span>  
  
 [<span data-ttu-id="4174e-155">Planungs-Assistent &#40;Data Mining-Add-Ins für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4174e-155">Forecast Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](forecast-wizard-data-mining-add-ins-for-excel.md)  
  
## <a name="highlight-exceptions-analyze"></a><span data-ttu-id="4174e-156">Ausnahmen hervorheben (Analysieren)</span><span class="sxs-lookup"><span data-stu-id="4174e-156">Highlight Exceptions (Analyze)</span></span>  
 <span data-ttu-id="4174e-157">Das Tool **Ausnahmen hervorheben** analysiert Muster in einer Datentabelle und findet Zeilen und Werte, die nicht dem Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="4174e-157">The **Highlight Exceptions** tool analyzes patterns in a table of data and finds rows and values that don't fit the pattern.</span></span> <span data-ttu-id="4174e-158">Sie können diese anschließend überprüfen und korrigieren und dann das Modell erneut ausführen oder Werte für spätere Maßnahmen mit Flags versehen.</span><span class="sxs-lookup"><span data-stu-id="4174e-158">You can then review and correct them and rerun the model, or flag values for later action.</span></span>  
  
 <span data-ttu-id="4174e-159">Das Tool **Ausnahmen hervorheben** verwendet den Microsoft Clustering-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="4174e-159">The **Highlight Exceptions** tool uses the Microsoft Clustering algorithm.</span></span>  
  
 [<span data-ttu-id="4174e-160">Ausnahmen &#40;Tabellenanalyse Tools für Excel markieren&#41;</span><span class="sxs-lookup"><span data-stu-id="4174e-160">Highlight Exceptions &#40;Table Analysis Tools for Excel&#41;</span></span>](highlight-exceptions-table-analysis-tools-for-excel.md)  
  
## <a name="prediction-calculator-analyze"></a><span data-ttu-id="4174e-161">Vorhersagerechner (Analysieren)</span><span class="sxs-lookup"><span data-stu-id="4174e-161">Prediction Calculator (Analyze)</span></span>  
 <span data-ttu-id="4174e-162">Dieses Tool erstellt ein Modell, in dem die Faktoren analysiert werden, die zu den Zielergebnissen führen. Anschließend wird ein Ergebnis für neue Eingaben vorhergesagt, wobei aus diesen Mustern abgeleitete Kriterien zugrunde gelegt werden. Zudem wird ein interaktives Arbeitsblatt zur Entscheidungsfindung generiert, in dem Sie neue Eingaben auf einfache Weise bewerten können.</span><span class="sxs-lookup"><span data-stu-id="4174e-162">This tool creates a model that analyzes the factors leading to target outcomes, and then predicts a result for any new input, based on criteria derived from these patterns It also generates an interactive decision making worksheet that lets you easily score new inputs.</span></span> <span data-ttu-id="4174e-163">Sie können das Bewertungsarbeitsblatt auch ausdrucken und offline nutzen.</span><span class="sxs-lookup"><span data-stu-id="4174e-163">You can also create a printed version of the scoring worksheet for offline use.</span></span>  
  
 <span data-ttu-id="4174e-164">Das **Vorhersagerechner** Tool verwendet den Microsoft Logistic Regression-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="4174e-164">The **Prediction Calculator** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 [<span data-ttu-id="4174e-165">Vorhersagerechner &#40;Tabellenanalyse Tools für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4174e-165">Prediction Calculator &#40;Table Analysis Tools for Excel&#41;</span></span>](prediction-calculator-table-analysis-tools-for-excel.md)  
  
## <a name="scenario-goal-seek-analyze"></a><span data-ttu-id="4174e-166">Szenario: Zielsuche (Analysieren)</span><span class="sxs-lookup"><span data-stu-id="4174e-166">Scenario: Goal Seek (Analyze)</span></span>  
 <span data-ttu-id="4174e-167">Im **zielsuchtool** geben Sie einen Zielwert an, und das Tool identifiziert die zugrunde liegenden Faktoren, die geändert werden müssen, um dieses Ziel zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="4174e-167">In the **Goal Seek** tool, you specify a target value, and the tool identifies the underlying factors that must change to meet that target.</span></span> <span data-ttu-id="4174e-168">Wenn Ihnen beispielsweise bekannt ist, dass die Kundenzufriedenheit in Bezug auf Anrufe um 20 % gesteigert werden muss, können Sie das Modell anweisen, die Faktoren vorherzusagen, die zum Erreichen dieses Ziels geändert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4174e-168">For example, if you know that you must increase call satisfaction by 20%, you can ask the model to predict the factors that should change to produce that goal.</span></span>  
  
 <span data-ttu-id="4174e-169">Das Tool zur **Zielsuche** verwendet den Microsoft Logistic Regression-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="4174e-169">The **Goal Seek** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 <span data-ttu-id="4174e-170">Details</span><span class="sxs-lookup"><span data-stu-id="4174e-170">details</span></span>  
  
 [<span data-ttu-id="4174e-171">Zielsuchszenario &#40;Tabellenanalyse Tools für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4174e-171">Goal Seek Scenario &#40;Table Analysis Tools for Excel&#41;</span></span>](goal-seek-scenario-table-analysis-tools-for-excel.md)  
  
## <a name="scenario-what-if-scenario-analyze"></a><span data-ttu-id="4174e-172">Szenario: Was-wäre-wenn-Szenario (Analysieren)</span><span class="sxs-lookup"><span data-stu-id="4174e-172">Scenario: What-If Scenario (Analyze)</span></span>  
 <span data-ttu-id="4174e-173">Das Tool **Was-wäre-wenn-Analyse** ergänzt das Tool zur **Zielsuche** .</span><span class="sxs-lookup"><span data-stu-id="4174e-173">The **What-If Analysis** tool complements the **Goal Seek** tool.</span></span> <span data-ttu-id="4174e-174">Bei diesem Tool geben Sie den Wert ein, der geändert werden soll. Das Modell trifft eine Vorhersage, ob die betreffende Änderung zum Erreichen des gewünschten Ergebnisses ausreichend ist.</span><span class="sxs-lookup"><span data-stu-id="4174e-174">With this tool, you entered the value you want to change, and the model predicts whether that change will be sufficient to achieve the desired outcome.</span></span> <span data-ttu-id="4174e-175">Sie können beispielsweise das Modell anweisen abzuleiten, ob durch den Einsatz eines zusätzlichen Callcenter-Mitarbeiters die Kundenzufriedenheit um einen Punkt steigt.</span><span class="sxs-lookup"><span data-stu-id="4174e-175">For example, you might ask the model to infer whether adding one extra call operator would increase customer satisfaction by one point.</span></span>  
  
 <span data-ttu-id="4174e-176">Das **Was-wäre-wenn-** Tool verwendet den Microsoft Logistic Regression-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="4174e-176">The **What-If** tool uses the Microsoft Logistic Regression algorithm.</span></span>  
  
 [<span data-ttu-id="4174e-177">Was-wäre-wenn-Szenario &#40;Tabellenanalyse Tools für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4174e-177">What-If Scenario &#40;Table Analysis Tools for Excel&#41;</span></span>](what-if-scenario-table-analysis-tools-for-excel.md)  
  
## <a name="shopping-basket-analysis-analyze"></a><span data-ttu-id="4174e-178">Warenkorbanalyse (Analysieren)</span><span class="sxs-lookup"><span data-stu-id="4174e-178">Shopping Basket Analysis (Analyze)</span></span>  
 <span data-ttu-id="4174e-179">Das **waren Korb Analyse** -Tool erstellt Gruppen von Produkten, die häufig in Kauf genommen werden, um Muster zu identifizieren, die bei Cross-Selling oder Up-Selling verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="4174e-179">The **Shopping Basket Analysis** tool creates groups of products that are frequently purchased together, to identify patterns that can be used in cross-selling or up-selling.</span></span> <span data-ttu-id="4174e-180">Zudem werden Berichte auf der Grundlage der Preise und Kosten für Bündel zusammengehöriger Produkte generiert, um die Entscheidungsfindung zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="4174e-180">It also generates reports based on the price and cost of related product bundles, to aid in decision-making.</span></span>  
  
 <span data-ttu-id="4174e-181">Sie können dieses Tool für häufig zusammen auftretende Ereignisse, Faktoren für eine Diagnose oder sonstige potenzielle Ursachen und Ergebnisse verwenden.</span><span class="sxs-lookup"><span data-stu-id="4174e-181">You can also use this tool for events that frequently occur together, factors leading to a diagnosis, or any other set of potential causes and outcomes.</span></span>  
  
 <span data-ttu-id="4174e-182">Das **waren Korb Analyse** Tool verwendet den Microsoft Association-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="4174e-182">The **Shopping Basket Analysis** tool uses the Microsoft Association algorithm.</span></span>  
  
 [<span data-ttu-id="4174e-183">Waren Korb Analyse &#40;Tabellenanalyse für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4174e-183">Shopping Basket Analysis &#40;Table AnalysisTools for Excel&#41;</span></span>](shopping-basket-analysis-table-analysistools-for-excel.md)  
  
## <a name="see-also"></a><span data-ttu-id="4174e-184">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4174e-184">See Also</span></span>  
 <span data-ttu-id="4174e-185">[Durchsuchen und Bereinigen von Daten](exploring-and-cleaning-data.md) </span><span class="sxs-lookup"><span data-stu-id="4174e-185">[Exploring and Cleaning Data](exploring-and-cleaning-data.md) </span></span>  
 <span data-ttu-id="4174e-186">[Validieren von Modellen und Verwenden von Modellen für Vorhersage &#40;Data Mining-Add-Ins für Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="4174e-186">[Validating Models and Using Models for Prediction &#40;Data Mining Add-ins for Excel&#41;](validating-models-and-using-models-for-prediction-data-mining-add-ins-for-excel.md) </span></span>  
 [<span data-ttu-id="4174e-187">Bereitstellen und Skalieren von Mining Modellen &#40;Data Mining-Add-Ins für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4174e-187">Deploying and Scaling Mining Models &#40;Data Mining Add-ins for Excel&#41;</span></span>](deploying-and-scaling-mining-models-data-mining-add-ins-for-excel.md)  
  
  
