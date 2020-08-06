---
title: Wichtige Einflussfaktoren analysieren (Tabellenanalyse Tools für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- key influencers
- factor analysis
ms.assetid: 54d7b4ce-7b79-407a-985c-aa655ad19280
author: minewiskan
ms.author: owend
ms.openlocfilehash: f60eb5144059b0976d52eec2329f27553132146c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610385"
---
# <a name="analyze-key-influencers-table-analysis-tools-for-excel"></a><span data-ttu-id="a2591-102">Wichtige Einflussfaktoren analysieren (Tabellenanalysetools für Excel)</span><span class="sxs-lookup"><span data-stu-id="a2591-102">Analyze Key Influencers (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="a2591-103">![Schaltfläche "Wichtige Einflussfaktoren analysieren" in Menüband](media/tat-aki.gif "Schaltfläche "Wichtige Einflussfaktoren analysieren" in Menüband")</span><span class="sxs-lookup"><span data-stu-id="a2591-103">![Analyze Key Influencers button in ribbon](media/tat-aki.gif "Analyze Key Influencers button in ribbon")</span></span>  
  
 <span data-ttu-id="a2591-104">Mit dem Tool **wichtige Einflussfaktoren analysieren** wählen Sie eine Spalte aus, die ein Zielergebnis enthält, und der Algorithmus bestimmt, welche Faktoren den stärksten Einfluss auf das Ergebnis hatten.</span><span class="sxs-lookup"><span data-stu-id="a2591-104">With the **Analyze Key Influencers** tool, you choose a column that contains a target outcome, and the algorithm determines which factors had the strongest influence on the outcome.</span></span>  
  
 <span data-ttu-id="a2591-105">Im Tool werden neue Datentabellen erstellt, in denen die zu jedem Ergebnis gehörenden Faktoren aufgeführt und die Beziehungswahrscheinlichkeit grafisch dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="a2591-105">The tool creates new data tables that report the factors associated with each outcome and graphically displays the probability of the relationship.</span></span> <span data-ttu-id="a2591-106">Sie können die Tabellen nach verschiedenen Faktoren und Ergebnissen filtern, um die Resultate ausführlicher zu prüfen.</span><span class="sxs-lookup"><span data-stu-id="a2591-106">You can filter the tables by different factors and outcomes to explore the results in more depth.</span></span>  
  
 <span data-ttu-id="a2591-107">Sie können auch zwei mögliche Ergebnisse auswählen und diese miteinander vergleichen.</span><span class="sxs-lookup"><span data-stu-id="a2591-107">You can also select a pair of possible outcomes and compare them.</span></span> <span data-ttu-id="a2591-108">Beispielsweise können Sie verschiedene Verbrauchergruppen vergleichen, um mögliche Faktoren für die Entscheidungsfindung zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="a2591-108">For example, you might compare different groups of consumers to determine possible decision-making factors.</span></span>  
  
## <a name="using-the-analyze-key-influencers-tool"></a><span data-ttu-id="a2591-109">Verwenden des Tools Wichtige Einflussfaktoren analysieren</span><span class="sxs-lookup"><span data-stu-id="a2591-109">Using the Analyze Key Influencers Tool</span></span>  
  
1.  <span data-ttu-id="a2591-110">Öffnen Sie eine Excel-Datentabelle.</span><span class="sxs-lookup"><span data-stu-id="a2591-110">Open an Excel data table.</span></span>  
  
2.  <span data-ttu-id="a2591-111">Klicken Sie in **Tabellen Tools**auf dem Menüband **analysieren** auf **wichtige Einflussfaktoren analysieren.**</span><span class="sxs-lookup"><span data-stu-id="a2591-111">In **Table Tools**, on the **Analyze** ribbon, click **Analyze Key Influencers.**</span></span>  
  
3.  <span data-ttu-id="a2591-112">Öffnen Sie die Spalte, die das Ziel der Analyse darstellt.</span><span class="sxs-lookup"><span data-stu-id="a2591-112">Select the single column that is the target of analysis.</span></span>  
  
4.  <span data-ttu-id="a2591-113">Klicken Sie optional auf **Spalten auswählen, die für die Analyse verwendet werden sollen**.</span><span class="sxs-lookup"><span data-stu-id="a2591-113">Optionally, click **Choose columns to be used for analysis**.</span></span> <span data-ttu-id="a2591-114">Wählen Sie im Dialogfeld **Erweiterte Spaltenauswahl** die Spalten aus, die am wahrscheinlichsten relevante Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="a2591-114">In the **Advanced Columns Selection** dialog box, choose the columns that are most likely to contain relevant data.</span></span> <span data-ttu-id="a2591-115">Um Leistung und Genauigkeit zu verbessern, heben Sie die Auswahl von Spalten wie ID oder Name auf, die für die Musteranalyse irrelevant sind.</span><span class="sxs-lookup"><span data-stu-id="a2591-115">To improve performance and accuracy, deselect columns such as ID or name that are unimportant for pattern analysis.</span></span> <span data-ttu-id="a2591-116">Klicken Sie auf **OK** , um das Dialogfeld **Erweiterte Spaltenauswahl** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="a2591-116">Click **OK** to close the **Advanced Columns Selection** dialog box.</span></span>  
  
5.  <span data-ttu-id="a2591-117">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="a2591-117">Click **Run**.</span></span>  
  
     <span data-ttu-id="a2591-118">Das Tool **wichtige Einflussfaktoren analysieren** führt eine Analyse der Daten durch, um die optimalen Einstellungen zu ermitteln, und legt alle Parameter automatisch fest.</span><span class="sxs-lookup"><span data-stu-id="a2591-118">The **Analyze Key Influencers** tool conducts an analysis of the data to determine the optimum settings, and sets all parameters automatically.</span></span>  
  
6.  <span data-ttu-id="a2591-119">Wenn keine Muster erkannt werden, erstellt der Assistent ein neues Arbeitsblatt, das eine Beschreibung des Problems enthält.</span><span class="sxs-lookup"><span data-stu-id="a2591-119">If no patterns were detected, the wizard creates a new worksheet that contains a description of the problem.</span></span>  
  
7.  <span data-ttu-id="a2591-120">Wenn Muster erkannt werden, erstellt der Assistent auf einem neuen Arbeitsblatt einen Bericht, der die Muster enthält.</span><span class="sxs-lookup"><span data-stu-id="a2591-120">If patterns are detected, the wizard creates a report on a new worksheet that shows the patterns.</span></span> <span data-ttu-id="a2591-121">Der Bericht hat den Namen \*\*Key-Einflussfaktoren \<column> für \*\*.</span><span class="sxs-lookup"><span data-stu-id="a2591-121">The report is named **Key Influencers for \<column>**.</span></span> <span data-ttu-id="a2591-122">Sie haben folgende Möglichkeiten, den Bericht anzupassen:</span><span class="sxs-lookup"><span data-stu-id="a2591-122">You can customize the report as described in the following procedure.</span></span>  
  
#### <a name="create-a-custom-report"></a><span data-ttu-id="a2591-123">Erstellen eines benutzerdefinierten Berichts</span><span class="sxs-lookup"><span data-stu-id="a2591-123">Create a custom report</span></span>  
  
1.  <span data-ttu-id="a2591-124">Wählen Sie **in der** Dropdown Liste Wert 1 und Wert 2 die zwei zu vergleichenden Werte in der Dropdown Liste **Wert 1** und **Wert 2** aus.</span><span class="sxs-lookup"><span data-stu-id="a2591-124">In the **Discrimination based on key influencers** dialog box, choose the two values that you want to compare by selecting them from the **Value 1** and **Value 2** dropdown lists.</span></span> <span data-ttu-id="a2591-125">Sie können zum Beispiel Käufer und Nicht-Käufer vergleichen.</span><span class="sxs-lookup"><span data-stu-id="a2591-125">For example, you might compare buyers to non-buyers.</span></span>  
  
2.  <span data-ttu-id="a2591-126">Klicken Sie auf **Bericht hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a2591-126">Click **Add Report**.</span></span>  
  
     <span data-ttu-id="a2591-127">Im Assistenten wird ein neues Arbeitsblatt erstellt und für jedes Paar von Schlüsselfaktorvergleichen eine Tabelle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a2591-127">The wizard creates a new worksheet and adds a table for each pair of key factor comparisons.</span></span>  
  
3.  <span data-ttu-id="a2591-128">Wenn Sie die Vergleiche abgeschlossen haben, klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="a2591-128">When you are done making comparisons, click **Close**.</span></span>  
  
## <a name="understanding-the-key-influencers-report"></a><span data-ttu-id="a2591-129">Grundlegendes zum Bericht der wichtigen Einflussfaktoren</span><span class="sxs-lookup"><span data-stu-id="a2591-129">Understanding the Key Influencers Report</span></span>  
 <span data-ttu-id="a2591-130">Nachdem das Datenmodell erstellt wurde, erstellt das Tool **wichtige Einflussfaktoren analysieren** Berichte, die Ihnen helfen, wichtige Einflussfaktoren zu untersuchen und zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="a2591-130">After the data model has been created, the **Analyze Key Influencers** tool creates reports that help you explore and compare key influencers.</span></span>  
  
-   <span data-ttu-id="a2591-131">Der Bericht auf der linken Seite wird standardmäßig generiert.</span><span class="sxs-lookup"><span data-stu-id="a2591-131">The report on the left side is the one generated by default.</span></span> <span data-ttu-id="a2591-132">Außerdem werden hier die stärksten Indikatoren der Ergebnisspalte angezeigt (die abhängige Variable).</span><span class="sxs-lookup"><span data-stu-id="a2591-132">It shows the strongest predictors of the outcome column (the dependent variable).</span></span>  
  
-   <span data-ttu-id="a2591-133">Der Bericht auf der rechten Seite ist optional. Sie können ihn erstellen, indem Sie zwei bestimmten Ergebniswerte vergleichen.</span><span class="sxs-lookup"><span data-stu-id="a2591-133">The report on the right side is optional, which you can create by comparing two specific outcome values.</span></span> <span data-ttu-id="a2591-134">Dieser Bericht vergleicht Käufer und Nicht-Käufer.</span><span class="sxs-lookup"><span data-stu-id="a2591-134">This report compares buyers and non-buyers.</span></span>  
  
-   <span data-ttu-id="a2591-135">Beachten Sie, dass für jeden Bericht ein neues Arbeitsblatt hinzugefügt wird, den Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="a2591-135">Note that a new worksheet is added for each report that you create.</span></span> <span data-ttu-id="a2591-136">Sie können die Tabellen verschieben, nachdem sie erstellt wurden; sie werden für den Vergleich nebeneinander platziert.</span><span class="sxs-lookup"><span data-stu-id="a2591-136">You can move the tables after they are created; we placed them side by side for comparison.</span></span>  
  
 <span data-ttu-id="a2591-137">![DM13](media/dm13-tat-aki-report.gif "DM13")</span><span class="sxs-lookup"><span data-stu-id="a2591-137">![DM13](media/dm13-tat-aki-report.gif "DM13")</span></span>  
  
 <span data-ttu-id="a2591-138">**Relative Auswirkung**</span><span class="sxs-lookup"><span data-stu-id="a2591-138">**Relative Impact**</span></span>  
 <span data-ttu-id="a2591-139">Der schattierte Balken im ersten Bericht gibt die Gewichtung der Zuordnung dieses Attributs zu dem Ergebnis an.</span><span class="sxs-lookup"><span data-stu-id="a2591-139">The shaded bar in the first report indicates the strength of the association of this attribute with the outcome.</span></span>  
  
 <span data-ttu-id="a2591-140">Die Länge des Balkens gibt die Wahrscheinlichkeit an, dass der Faktor zum Ergebnis beiträgt. Je länger der schattierte Balken also ist, desto stärker ist die Verknüpfung.</span><span class="sxs-lookup"><span data-stu-id="a2591-140">The length of the bar indicates the probability that the factor contributes to the outcome; therefore, the longer the shaded bar, the stronger the association.</span></span>  
  
 <span data-ttu-id="a2591-141">**Begünstigt**</span><span class="sxs-lookup"><span data-stu-id="a2591-141">**Favors**</span></span>  
 <span data-ttu-id="a2591-142">Im zweiten Bericht werden die Zielwerte, die Sie vergleichen, in zwei Spalten aufgeführt. Die zugehörigen Faktoren werden in absteigender Reihenfolge (in Bezug auf die Zuverlässigkeit) aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a2591-142">In the second report, the target values that you compare are listed in two columns, with the related factors listed in order of descending confidence.</span></span>  
  
-   <span data-ttu-id="a2591-143">Der **blaue** Balken zeigt Attribute an, die zum Ergebnis beitragen, "No" (= nicht gekauft).</span><span class="sxs-lookup"><span data-stu-id="a2591-143">The **blue** bar shows attributes contributing to the outcome, "No" (=did not purchase).</span></span>  
  
-   <span data-ttu-id="a2591-144">Der **Rote** Balken zeigt Attribute an, die zum Ergebnis beitragen, "yes" (= ein Fahrrad gekauft).</span><span class="sxs-lookup"><span data-stu-id="a2591-144">The **red** bar shows attributes contributing to the outcome, "Yes" (=purchased a bike).</span></span>  
  
 <span data-ttu-id="a2591-145">Die Farben in der schattierten Leiste sind beliebig wählbar.</span><span class="sxs-lookup"><span data-stu-id="a2591-145">The colors in the shading bar are arbitrary.</span></span> <span data-ttu-id="a2591-146">Sie können diese Farben ändern, indem Sie die Optionen für Tabellenentwurf in Excel festlegen.</span><span class="sxs-lookup"><span data-stu-id="a2591-146">You can change these colors by setting the options for table design in Excel.</span></span>  
  
 <span data-ttu-id="a2591-147">In einem Bericht, der zwei Werte miteinander vergleicht, werden die wichtigen Einflussfaktoren im zweiten Bericht nach ihrer Auswirkung auf die Zielwerte sortiert.</span><span class="sxs-lookup"><span data-stu-id="a2591-147">In a report that contrasts two values, the second report ranks the key influencers by the amount of impact on the target values.</span></span>  
  
 <span data-ttu-id="a2591-148">Da alle Diagramme auf Excel-Tabellen basieren, können Sie die Tabellen filtern und sortieren, um sich auf bestimmte Faktoren oder Ergebnisse zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="a2591-148">Because all the charts are based on Excel tables, you can filter and sort to focus on specific factors or outcomes.</span></span>  
  
## <a name="more-about-the-analyze-key-influencers-tool"></a><span data-ttu-id="a2591-149">Weitere Informationen zum Tool "Wichtige Einflussfaktoren analysieren"</span><span class="sxs-lookup"><span data-stu-id="a2591-149">More About the Analyze Key Influencers Tool</span></span>  
 <span data-ttu-id="a2591-150">Wenn das Tool **wichtige Einflussfaktoren analysieren** die Daten analysiert, werden folgende Aktionen durchführt:</span><span class="sxs-lookup"><span data-stu-id="a2591-150">When the **Analyze Key Influencers** tool analyzes your data, it does the following:</span></span>  
  
-   <span data-ttu-id="a2591-151">Es wird eine Datenstruktur erstellt, in der wichtige Informationen zur Verteilung von Daten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="a2591-151">Creates a data structure that stores key information about the distribution of your data.</span></span>  
  
-   <span data-ttu-id="a2591-152">Erstellt ein Modell mithilfe des Microsoft Naïve Bayes-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="a2591-152">Creates a model using the Microsoft Naïve Bayes algorithm.</span></span>  
  
-   <span data-ttu-id="a2591-153">Erstellt Vorhersagen, die jede Datenspalte mit dem angegebenen Ergebnis korrelieren.</span><span class="sxs-lookup"><span data-stu-id="a2591-153">Creates predictions that correlates each column of data with the specified outcome.</span></span>  
  
-   <span data-ttu-id="a2591-154">Verwendet das Vertrauensergebnis für jede Vorhersage, um die Faktoren zu identifizieren, die sich beim Erzeugen des Zielergebnisses am meisten ausgewirkt haben.</span><span class="sxs-lookup"><span data-stu-id="a2591-154">Uses the confidence score for each of the predictions to identify the factors that are the most influential in producing the targeted outcome.</span></span>  
  
-   <span data-ttu-id="a2591-155">Erstellt einen Bericht, der die wichtigen Einflussfaktoren beschreibt, die nach dem Vertrauensergebnis sortiert sind.</span><span class="sxs-lookup"><span data-stu-id="a2591-155">Creates a report describing the key influencers, ordered by confidence scores.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="a2591-156">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a2591-156">Requirements</span></span>  
 <span data-ttu-id="a2591-157">Wenn die Zielspalte kontinuierliche numerische Werte enthält, werden die numerischen Werte vom Tool automatisch in Gruppen unterteilt.</span><span class="sxs-lookup"><span data-stu-id="a2591-157">If the target column contains continuous numeric values, the tool automatically segments the numeric values into groups.</span></span> <span data-ttu-id="a2591-158">Diese Gruppierungen stellen Cluster von Fällen mit ähnlichen Merkmalen dar.</span><span class="sxs-lookup"><span data-stu-id="a2591-158">These groupings represent clusters of cases that have similar characteristics.</span></span> <span data-ttu-id="a2591-159">Numerische Werte können jedoch nicht in benutzerfreundliche Gruppen aufgeteilt werden.</span><span class="sxs-lookup"><span data-stu-id="a2591-159">However, numeric values might not be divided into user-friendly groups.</span></span> <span data-ttu-id="a2591-160">Der Bericht kann z. b. eine Gruppierung wie z. b. " \< 12,85701" enthalten, während Berichts Benutzer in der Regel Gruppierungen mit ganzen Zahlen, wie z. b. 10-19, 20-29 usw., sehen.</span><span class="sxs-lookup"><span data-stu-id="a2591-160">For example, the report might contain a grouping such as "\<12.85701", whereas report users typically like to see groupings that use whole numbers, such as 10-19, 20-29, and so on.</span></span>  
  
 <span data-ttu-id="a2591-161">Wenn Sie numerische Daten anders gruppieren möchten, müssen Sie die Daten vor der Analyse entsprechend segmentieren.</span><span class="sxs-lookup"><span data-stu-id="a2591-161">If you want to group numeric data in a different way, you must segment the data the way you want before creating the analysis.</span></span> <span data-ttu-id="a2591-162">Beispielsweise können Sie [das Tool neu](relabel-sql-server-data-mining-add-ins.md) bezeichnen im Data Mining-Client für Excel verwenden, um eine neue Gruppierungs Bezeichnung in einer separaten Spalte zu erstellen, und dann nur diese neue Spalte in der Analyse verwenden.</span><span class="sxs-lookup"><span data-stu-id="a2591-162">For example, you can use the [Relabel](relabel-sql-server-data-mining-add-ins.md) tool in the Data Mining Client for Excel to create a new grouping label in a separate column, and then use only that new column in analysis.</span></span>  
  
### <a name="related-tools"></a><span data-ttu-id="a2591-163">Verwandte Tools</span><span class="sxs-lookup"><span data-stu-id="a2591-163">Related Tools</span></span>  
 <span data-ttu-id="a2591-164">Das **Data Mining** -Menüband bietet erweiterte Tools, einschließlich der Möglichkeit zum Anpassen von Data Mining Modellen.</span><span class="sxs-lookup"><span data-stu-id="a2591-164">The **Data Mining** ribbon provides more advanced tools, including the ability to customize data mining models</span></span>  
  
 <span data-ttu-id="a2591-165">Wenn Sie das Modell mit dem Tool **wichtige Einflussfaktoren analysieren** speichern, können Sie den Data Mining-Client verwenden, um das Modell zu durchsuchen und die Beziehungen ausführlicher zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="a2591-165">If you save your model by using the **Analyze Key Influencers** tool, you can use the Data Mining Client to browse the model and explore relationships in more detail.</span></span> <span data-ttu-id="a2591-166">Weitere Informationen finden Sie unter durch [Suchen von Modellen in Excel &#40;SQL Server Data Mining-Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="a2591-166">For information, see [Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;](browsing-models-in-excel-sql-server-data-mining-add-ins.md).</span></span> <span data-ttu-id="a2591-167">Sie können mithilfe von Microsoft Office Visio Diagramme erstellen, die Beziehungen als Cluster oder Abhängigkeitsnetzwerke anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a2591-167">You can also use Microsoft Office Visio to create charts and diagrams that display the relationships as cluster or as dependency networks.</span></span> <span data-ttu-id="a2591-168">Weitere Informationen finden Sie unter [Problembehandlung für Visio Data Mining-Diagramme &#40;SQL Server Data Mining-Add-ins&#41;](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="a2591-168">For more information, see [Troubleshooting Visio Data Mining Diagrams &#40;SQL Server Data Mining Add-ins&#41;](troubleshooting-visio-data-mining-diagrams-sql-server-data-mining-add-ins.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a2591-169">Die mit den Tabellenanalysetools erstellten Modelle werden gelöscht, wenn Sie das Arbeitsblatt schließen oder die Verbindung mit dem [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Server beenden.</span><span class="sxs-lookup"><span data-stu-id="a2591-169">The models that are created when you use the Table Analysis Tools are deleted when you close your worksheet or terminate the connection with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server.</span></span> <span data-ttu-id="a2591-170">Daher können Sie die Modelle nur durchsuchen, solange die Verbindung bestehen bleibt.</span><span class="sxs-lookup"><span data-stu-id="a2591-170">Therefore, you can only browse the models as long as the connection remains open.</span></span> <span data-ttu-id="a2591-171">Sie können die Modelle nicht in Visio rendern, wenn Sie die Verbindung beenden oder das Arbeitsblatt schließen.</span><span class="sxs-lookup"><span data-stu-id="a2591-171">You cannot render the models in Visio if you close the connection or close the worksheet.</span></span>  
  
 <span data-ttu-id="a2591-172">Weitere Informationen zum Algorithmus, der vom Tool **wichtige Einflussfaktoren analysieren** verwendet wird, finden Sie unter "Microsoft Naive Bayes-Algorithmus" in SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="a2591-172">For more information about the algorithm used by the **Analyze Key Influencers** tool, see "Microsoft Naïve Bayes Algorithm" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2591-173">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a2591-173">See Also</span></span>  
 <span data-ttu-id="a2591-174">[Tabellenanalyse Tools für Excel](table-analysis-tools-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="a2591-174">[Table Analysis Tools for Excel](table-analysis-tools-for-excel.md) </span></span>  
 [<span data-ttu-id="a2591-175">Erstellen eines Data Mining-Modells</span><span class="sxs-lookup"><span data-stu-id="a2591-175">Creating a Data Mining Model</span></span>](creating-a-data-mining-model.md)  
  
  
