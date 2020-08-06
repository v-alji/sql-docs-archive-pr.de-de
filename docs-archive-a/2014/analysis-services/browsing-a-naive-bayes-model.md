---
title: Durchsuchen eines Naive Bayes-Modells | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f9160b48-3beb-439c-9694-f084e1afa625
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3b0d18cd74e71f1ef18bffd6b0998e0b326e887a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610311"
---
# <a name="browsing-a-naive-bayes-model"></a><span data-ttu-id="8dbab-102">Durchsuchen eines Naive Bayes-Modells</span><span class="sxs-lookup"><span data-stu-id="8dbab-102">Browsing a Naive Bayes Model</span></span>
  <span data-ttu-id="8dbab-103">Wenn Sie ein Naive Bayes-Modell mithilfe von **Durchsuchen**öffnen, wird das Modell in einem interaktiven Viewer mit vier verschiedenen Bereichen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8dbab-103">When you open a Naïve Bayes model using **Browse**, the model is displayed in an interactive viewer with four different panes.</span></span> <span data-ttu-id="8dbab-104">Verwenden Sie den Viewer, um Korrelationen zu untersuchen sowie um Informationen zum Modell und den zugrunde liegenden Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8dbab-104">Use the viewer to explore correlations, and get information about the model and the underlying data.</span></span>  
  
-   [<span data-ttu-id="8dbab-105">Abhängigkeitsnetzwerk</span><span class="sxs-lookup"><span data-stu-id="8dbab-105">Dependency Network</span></span>](#bkmk_DepNet)  
  
-   [<span data-ttu-id="8dbab-106">Attribut profile</span><span class="sxs-lookup"><span data-stu-id="8dbab-106">Attribute Profiles</span></span>](#bkmk_AttProf)  
  
-   [<span data-ttu-id="8dbab-107">Attributmerkmale</span><span class="sxs-lookup"><span data-stu-id="8dbab-107">Attribute Characteristics</span></span>](#bkmk_AttChar)  
  
-   [<span data-ttu-id="8dbab-108">Attributunterscheidung</span><span class="sxs-lookup"><span data-stu-id="8dbab-108">Attribute Discrimination</span></span>](#bkmk_AttDisc)  
  
##  <a name="explore-the-model"></a><a name="BKMK_Tabs"></a><span data-ttu-id="8dbab-109">Untersuchen des Modells</span><span class="sxs-lookup"><span data-stu-id="8dbab-109">Explore the Model</span></span>  
 <span data-ttu-id="8dbab-110">Der Zweck des Viewers besteht darin, die Interaktion zwischen Eingabe- und Ausgabeattributen (Eingaben und abhängigen Variablen) zu untersuchen, die vom [!INCLUDE[msCoName](../includes/msconame-md.md)] Naïve Bayes-Modell ermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="8dbab-110">The purpose of the viewer is to help you explore the interaction between input and output attributes (inputs and dependent variables) that were discovered by the [!INCLUDE[msCoName](../includes/msconame-md.md)] Naive Bayes model.</span></span>  
  
 <span data-ttu-id="8dbab-111">Wenn Sie mit dem Naive Bayes-Viewer experimentieren möchten, verwenden Sie den Assistenten zum [klassifizieren &#40;Data Mining-Add-Ins für Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) auf dem Menüband Data Mining, klicken Sie auf die Option **erweitert** , und ändern Sie den Algorithmus so, dass er den Naive Bayes-Algorithmus verwendet.</span><span class="sxs-lookup"><span data-stu-id="8dbab-111">If you want to experiment with the Naïve Bayes viewer, use the [Classify Wizard &#40;Data Mining Add-ins for Excel&#41;](classify-wizard-data-mining-add-ins-for-excel.md) wizard in the Data Mining ribbon, click the **Advanced** option, and change the algorithm to use the Naïve Bayes algorithm</span></span>  
  
 <span data-ttu-id="8dbab-112">In diesen Beispielen haben wir die Quelldaten in der Beispiel Arbeitsmappe verwendet und die Spalte " **Jahreseinkommen**" in fünf Einkommensgruppen gruppiert (von **sehr niedrig** bis **sehr hoch**).</span><span class="sxs-lookup"><span data-stu-id="8dbab-112">For these examples, we used the Source data in the sample workbook, and grouped the column, **Yearly Income**, into five income groups, from **Very Low** to **Very High**.</span></span> <span data-ttu-id="8dbab-113">Anhand des Naïve Bayes-Modells wurden anschließend die Faktoren analysiert, die mit den einzelnen Einkommenskategorien korrelierten.</span><span class="sxs-lookup"><span data-stu-id="8dbab-113">The Naïve Bayes model then analyzed the factors correlated with each income category.</span></span>  
  
###  <a name="dependency-network"></a><a name="bkmk_DepNet"></a><span data-ttu-id="8dbab-114">Abhängigkeits Netzwerk</span><span class="sxs-lookup"><span data-stu-id="8dbab-114">Dependency Network</span></span>  
 <span data-ttu-id="8dbab-115">Das erste Fenster, das Sie verwenden, ist das **Abhängigkeits Netzwerk**.</span><span class="sxs-lookup"><span data-stu-id="8dbab-115">The first window you'll use is the **Dependency Network**.</span></span> <span data-ttu-id="8dbab-116">Es zeigt auf einen Blick, welche Eingaben eng mit dem ausgewählten Ergebnis korrelieren.</span><span class="sxs-lookup"><span data-stu-id="8dbab-116">It shows you at a glance which inputs are closely correlated to the selected outcome.</span></span>  
  
 <span data-ttu-id="8dbab-117">![Abhängigkeitsnetzwerk in Naive Bayes-Viewer](media/dm13-nb.gif "Abhängigkeitsnetzwerk in Naive Bayes-Viewer")</span><span class="sxs-lookup"><span data-stu-id="8dbab-117">![dependency network in Naive Bayes viewer](media/dm13-nb.gif "dependency network in Naive Bayes viewer")</span></span>  
  
##### <a name="explore-the-dependency-network"></a><span data-ttu-id="8dbab-118">Untersuchen des Abhängigkeitsnetzwerks</span><span class="sxs-lookup"><span data-stu-id="8dbab-118">Explore the dependency network</span></span>  
  
1.  <span data-ttu-id="8dbab-119">Klicken Sie zuerst auf das Zielergebnis, **Jahreseinkommen**, das als Knoten im Diagramm dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8dbab-119">First, click the target outcome, **Yearly Income**, which is represented as a node in the graph.</span></span>  
  
     <span data-ttu-id="8dbab-120">Die hervorgehobenen Knoten, die die Zielvariable umschließen, sind die Knoten, die statistisch mit diesem Ergebnis korrelieren.</span><span class="sxs-lookup"><span data-stu-id="8dbab-120">The highlighted nodes surrounding the target variable are those that are statistically correlated with this outcome.</span></span> <span data-ttu-id="8dbab-121">Verwenden Sie die Legende im unteren Bereich des Viewers, um die Art der Beziehung zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="8dbab-121">Use the legend at the bottom of the viewer to understand the nature of the relationship.</span></span>  
  
2.  <span data-ttu-id="8dbab-122">Klicken Sie auf den Schieberegler auf der linken Seite des Viewers, und ziehen Sie ihn nach unten.</span><span class="sxs-lookup"><span data-stu-id="8dbab-122">Click the slider at the left of the viewer and drag it downward.</span></span>  
  
     <span data-ttu-id="8dbab-123">Durch dieses Steuerelement werden die unabhängigen Variablen nach der Stärke der Abhängigkeiten gefiltert.</span><span class="sxs-lookup"><span data-stu-id="8dbab-123">This control filters the independent variables, based on the strengths of the dependencies.</span></span> <span data-ttu-id="8dbab-124">Wenn Sie den Schieberegler nach unten ziehen, verbleiben nur die stärksten Links im Diagramm.</span><span class="sxs-lookup"><span data-stu-id="8dbab-124">When you drag the slider down, only the strongest links remain in the graph.</span></span>  
  
3.  <span data-ttu-id="8dbab-125">Nachdem Sie das Diagramm gefiltert haben, klicken Sie auf die Schaltfläche **Diagramm Ansicht kopieren**.</span><span class="sxs-lookup"><span data-stu-id="8dbab-125">After you have filtered the graph, click the button, **Copy Graph View**.</span></span> <span data-ttu-id="8dbab-126">Wählen Sie anschließend ein Arbeitsblatt in Excel aus, und drücken Sie STRG+V.</span><span class="sxs-lookup"><span data-stu-id="8dbab-126">Then select a worksheet in Excel, and press Ctrl+V.</span></span>  
  
     <span data-ttu-id="8dbab-127">Durch diese Option wird die ausgewählte Ansicht einschließlich Filtern und Hervorhebungen kopiert.</span><span class="sxs-lookup"><span data-stu-id="8dbab-127">This option copies the view that you have selected, including filters and highlighting.</span></span>  
  
 [<span data-ttu-id="8dbab-128">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="8dbab-128">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="attribute-profiles"></a><a name="bkmk_AttProf"></a> <span data-ttu-id="8dbab-129">Attributprofile</span><span class="sxs-lookup"><span data-stu-id="8dbab-129">Attribute Profiles</span></span>  
 <span data-ttu-id="8dbab-130">Die Fenster " **Attribut profile** " geben Ihnen einen visuellen Hinweis darauf, wie alle anderen Variablen mit den einzelnen Ergebnissen verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="8dbab-130">The **Attribute Profiles** windows gives you a visual indication of how all other variables are related to the individual outcomes.</span></span>  
  
##### <a name="explore-the-profiles"></a><span data-ttu-id="8dbab-131">Untersuchen der Profile</span><span class="sxs-lookup"><span data-stu-id="8dbab-131">Explore the profiles</span></span>  
  
1.  <span data-ttu-id="8dbab-132">Um einige Werte ausblenden, sodass Sie die Ergebnisse besser vergleichen können, klicken Sie auf die Spaltenüberschrift, und ziehen diese unter eine andere Spalte.</span><span class="sxs-lookup"><span data-stu-id="8dbab-132">To hide some values so that you can more easily compare outcomes, click the column heading and drag it under another column.</span></span>  
  
     <span data-ttu-id="8dbab-133">![Attributprofile in Naive Bayes-Viewer](media/dm13-nb-attprof.gif "Attributprofile in Naive Bayes-Viewer")</span><span class="sxs-lookup"><span data-stu-id="8dbab-133">![attribute profiles in Naive Bayes viewer](media/dm13-nb-attprof.gif "attribute profiles in Naive Bayes viewer")</span></span>  
  
2.  <span data-ttu-id="8dbab-134">Klicken Sie in eine beliebige Zelle, um die Verteilung der Werte in der **Mining Legende**anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8dbab-134">Click in any cell to view the distribution of values in the **Mining Legend**.</span></span>  
  
     <span data-ttu-id="8dbab-135">Da die Attribute, die den verschiedenen Ergebnissen zugeordnet sind, visuell angezeigt werden, erkennen Sie auf Anhieb interessante Korrelationen, z. B. die Einkommensverteilung nach Region.</span><span class="sxs-lookup"><span data-stu-id="8dbab-135">Because the attributes associated with different outcomes are displayed visually, it is easy to spot interesting correlations, such as how incomes are distributed by region.</span></span>  
  
3.  <span data-ttu-id="8dbab-136">Zum Abrufen der Daten, die dieser Ansicht zugrunde liegen, klicken Sie auf **nach Excel kopieren**.</span><span class="sxs-lookup"><span data-stu-id="8dbab-136">To obtain the data underlying this view, click **Copy to Excel**.</span></span> <span data-ttu-id="8dbab-137">Eine Tabelle wird in einem neuen Arbeitsblatt generiert, das die Korrelationen zwischen den einzelnen Attributen und Ergebnissen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="8dbab-137">A table is generated in a new worksheet that shows the correlations among individual attributes and outcomes.</span></span> <span data-ttu-id="8dbab-138">In dieser Excel-Tabelle können Sie Spalten einfach ausblenden oder filtern.</span><span class="sxs-lookup"><span data-stu-id="8dbab-138">In this Excel table you can easily hide or filter columns.</span></span>  
  
 [<span data-ttu-id="8dbab-139">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="8dbab-139">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="attribute-characteristics"></a><a name="bkmk_AttChar"></a><span data-ttu-id="8dbab-140">Attribut Merkmale</span><span class="sxs-lookup"><span data-stu-id="8dbab-140">Attribute Characteristics</span></span>  
 <span data-ttu-id="8dbab-141">Die Ansicht " **Attribut Merkmale** " ist nützlich für eine ausführliche Untersuchung einer bestimmten Ergebnis Variablen und der zugehörigen Faktoren.</span><span class="sxs-lookup"><span data-stu-id="8dbab-141">The **Attribute Characteristics** view is useful for in-depth examination of a particular outcome variable and the contributing factors.</span></span>  
  
 <span data-ttu-id="8dbab-142">![Attributmerkmale in Naive Bayes-Viewer](media/dm13-nb-viewer.gif "Attributmerkmale in Naive Bayes-Viewer")</span><span class="sxs-lookup"><span data-stu-id="8dbab-142">![attribute characteristics in Naive Bayes viewer](media/dm13-nb-viewer.gif "attribute characteristics in Naive Bayes viewer")</span></span>  
  
##### <a name="explore-the-attribute-characteristics"></a><span data-ttu-id="8dbab-143">Untersuchen der Attributeigenschaften</span><span class="sxs-lookup"><span data-stu-id="8dbab-143">Explore the attribute characteristics</span></span>  
  
1.  <span data-ttu-id="8dbab-144">Klicken Sie auf **Wert** , und wählen Sie ein Element aus dem **Wert**aus.</span><span class="sxs-lookup"><span data-stu-id="8dbab-144">Click **Value** and select an item from the **Value**.</span></span>  
  
     <span data-ttu-id="8dbab-145">Während Sie ein Zielergebnis auswählen, wird das Diagramm aktualisiert und zeigt nach Wichtigkeit sortiert die Faktoren an, die am stärksten mit dem Ergebnis verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="8dbab-145">As you select a target outcome, the graph updates to show the factors that are most strongly associated with the outcome, sorted by importance.</span></span>  
  
     <span data-ttu-id="8dbab-146">Beachten Sie Folgendes: Wenn Sie ein Modell mithilfe der Option [wichtige Einflussfaktoren analysieren &#40;Tabellenanalyse Tools für Excel&#41;](analyze-key-influencers-table-analysis-tools-for-excel.md) erstellen, können Sie Modelle erstellen, die mehr als ein vorhersagbares Attribut haben.</span><span class="sxs-lookup"><span data-stu-id="8dbab-146">Note that if you create a model using the [Analyze Key Influencers &#40;Table Analysis Tools for Excel&#41;](analyze-key-influencers-table-analysis-tools-for-excel.md) option, you can create models that have more than one predictable attribute.</span></span> <span data-ttu-id="8dbab-147">In allen anderen Assistenten der Data Mining-Add-Ins sind Sie jedoch auf ein vorhersagbares Attribut beschränkt.</span><span class="sxs-lookup"><span data-stu-id="8dbab-147">However, all other wizards in the Data Mining add-ins limit you to one predictable attribute.</span></span>  
  
2.  <span data-ttu-id="8dbab-148">Klicken Sie auf **nach Excel kopieren** , um eine Tabelle in einem neuen Arbeitsblatt zu erstellen, in der die Ergebnisse für alle Attribute aufgelistet sind, die mit dem ausgewählten Zielergebnis verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="8dbab-148">Click **Copy to Excel** to create a table, in a new worksheet, listing the scores for all attributes that are related to the selected target outcome.</span></span>  
  
 [<span data-ttu-id="8dbab-149">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="8dbab-149">Back To Top</span></span>](#BKMK_Tabs)  
  
###  <a name="attribute-discrimination"></a><a name="bkmk_AttDisc"></a><span data-ttu-id="8dbab-150">Attribut Unterscheidung</span><span class="sxs-lookup"><span data-stu-id="8dbab-150">Attribute Discrimination</span></span>  
 <span data-ttu-id="8dbab-151">Die Ansicht " **Attribut Unterscheidung** " unterstützt das Vergleichen zweier Ergebnisse oder eines Ergebnisses im Vergleich zu allen anderen Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="8dbab-151">The **Attribute Discrimination** view helps compare two outcomes, or one outcome vs. all other outcomes.</span></span>  
  
 <span data-ttu-id="8dbab-152">![Attributunterscheidung in Naive Bayes-Viewer](media/dm13-nb-attdisc.gif "Attributunterscheidung in Naive Bayes-Viewer")</span><span class="sxs-lookup"><span data-stu-id="8dbab-152">![attribute discrimination in Naive Bayes viewer](media/dm13-nb-attdisc.gif "attribute discrimination in Naive Bayes viewer")</span></span>  
  
##### <a name="explore-attribute-discrimination"></a><span data-ttu-id="8dbab-153">Untersuchen der Attributunterscheidung</span><span class="sxs-lookup"><span data-stu-id="8dbab-153">Explore attribute discrimination</span></span>  
  
1.  <span data-ttu-id="8dbab-154">Wählen Sie mit den Steuerelementen **Wert 1** und **Wert 2**die Ergebnisse aus, die Sie vergleichen möchten.</span><span class="sxs-lookup"><span data-stu-id="8dbab-154">Use the controls, **Value 1** and **Value 2**, to select the outcomes that you want to compare.</span></span>  
  
     <span data-ttu-id="8dbab-155">In diesem Modell gab es z. b. einige interessante Attribute in der Gruppe mit niedrigem Einkommen, daher haben wir die niedrigste Einkommensgruppe in der ersten Dropdown Liste ausgewählt und **alle anderen Zustände** in der zweiten Dropdown Liste ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="8dbab-155">For example, in this model there were some interesting attributes in the low income group, so we chose the lowest income group in the first dropdown list, and chose **All other states** in the second dropdown list.</span></span>  
  
     <span data-ttu-id="8dbab-156">Die Attribute werden nach Wichtigkeit sortiert (die auf Grundlage der Trainingsdaten berechnet wird).</span><span class="sxs-lookup"><span data-stu-id="8dbab-156">The attributes are sorted by order of importance (calculated based on the training data).</span></span> <span data-ttu-id="8dbab-157">Daher ist der Beruf der Faktor, der am stärksten mit dem Einkommen korreliert (zumindest bei dieser Zielgruppe).</span><span class="sxs-lookup"><span data-stu-id="8dbab-157">Therefore, occupation is the factor most closely correlated with income (for this target group, at least),</span></span>  
  
     <span data-ttu-id="8dbab-158">Um die genauen Abbildungen anzuzeigen, klicken Sie auf die farbige Leiste, und sehen Sie sich die **Mining Legende**an.</span><span class="sxs-lookup"><span data-stu-id="8dbab-158">To see the exact figures, click the colored bar and view the **Mining Legend**.</span></span>  
  
2.  <span data-ttu-id="8dbab-159">Beachten Sie, dass niedrigere Einkommen auch mit der Region Europa korreliert werden.</span><span class="sxs-lookup"><span data-stu-id="8dbab-159">Note that lower incomes are also correlated with the Europe region.</span></span>  
  
     <span data-ttu-id="8dbab-160">Das Naïve Bayes-Modell unterstützt keine Drilldowns. Wenn Sie jedoch den Fällen, die dieser Ergebnisgruppe zugeordnet sind, auf den Grund gehen möchten, können Sie eine Abfrage ausführen.</span><span class="sxs-lookup"><span data-stu-id="8dbab-160">The Naïve Bayes model does not support drilldown; however, if you wanted to investigate the cases associated with this outcome group, you could use a query.</span></span> <span data-ttu-id="8dbab-161">Informationen zu Abfragen für diesen Modelltyp finden Sie unter [Beispiele für Naive Bayes-Modell Abfragen](data-mining/naive-bayes-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="8dbab-161">For information about queries on this type of model, see [Naive Bayes Model Query Examples](data-mining/naive-bayes-model-query-examples.md).</span></span>  
  
 [<span data-ttu-id="8dbab-162">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="8dbab-162">Back To Top</span></span>](#BKMK_Tabs)  
  
## <a name="see-also"></a><span data-ttu-id="8dbab-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8dbab-163">See Also</span></span>  
 [<span data-ttu-id="8dbab-164">Durchsuchen von Modellen in Excel &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="8dbab-164">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
