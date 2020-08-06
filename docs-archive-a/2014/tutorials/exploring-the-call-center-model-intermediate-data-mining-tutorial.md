---
title: Untersuchen des Callcentermodells (Data Mining-Lernprogramm für Fortgeschrittene) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 9095212c-9068-4dd8-85ce-17a467adeabb
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2aceec298ba78e29988571293f8422ab9e55aa97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719123"
---
# <a name="exploring-the-call-center-model-intermediate-data-mining-tutorial"></a><span data-ttu-id="ea2f9-102">Prüfen des Callcentermodells (Data Mining-Lernprogramm für Fortgeschrittene)</span><span class="sxs-lookup"><span data-stu-id="ea2f9-102">Exploring the Call Center Model (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="ea2f9-103">Nachdem Sie nun das explorative Modell erstellt haben, können Sie es verwenden, um die Daten genauer zu untersuchen. Verwenden Sie dazu die folgenden Tools, die in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-103">Now that you have built the exploratory model, you can use it to learn more about your data by using the following tools provided in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="ea2f9-104">[Microsoft-Viewer für neuronale Netzwerke](#bkmk_NNviewer) **:** dieser Viewer ist im Data Mining-Designer auf der Registerkarte **Mining Modell-Viewer** verfügbar und soll Ihnen helfen, mit Interaktionen in den Daten zu experimentieren.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-104">[Microsoft Neural Network Viewer](#bkmk_NNviewer) **:** This viewer is available in the **Mining Model Viewer** tab of Data Mining Designer, and is designed to help you experiment with interactions in the data.</span></span>  
  
-   <span data-ttu-id="ea2f9-105">[Microsoft Generic Content Tree Viewer](#bkmk_genviewer) **:** dieser Standard-Viewer stellt ausführliche Details zu den Mustern und Statistiken bereit, die vom Algorithmus beim Generieren des Modells erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-105">[Microsoft Generic Content Tree Viewer](#bkmk_genviewer) **:** This standard viewer provides in-depth detail about the patterns and statistics discovered by the algorithm when it generated the model.</span></span>  
  
##  <a name="microsoft-neural-network-viewer"></a><a name="bkmk_NNviewer"></a><span data-ttu-id="ea2f9-106">Microsoft-Viewer für neuronale Netzwerke</span><span class="sxs-lookup"><span data-stu-id="ea2f9-106">Microsoft Neural Network Viewer</span></span>  
 <span data-ttu-id="ea2f9-107">Der Viewer enthält drei Bereiche: **Eingabe**, **Ausgabe**und **Variablen**.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-107">The viewer has three panes - **Input**, **Output**, and **Variables**.</span></span>  
  
 <span data-ttu-id="ea2f9-108">Mithilfe des **Ausgabe** Bereichs können Sie unterschiedliche Werte für das vorhersagbare Attribut oder die abhängige Variable auswählen.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-108">By using the **Output** pane, you can select different values for the predictable attribute, or dependent variable.</span></span> <span data-ttu-id="ea2f9-109">Wenn das Modell mehrere vorhersagbare Attribute enthält, können Sie das Attribut aus der Liste **Ausgabe Attribut** auswählen.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-109">If your model contains multiple predictable attributes, you can select the attribute from the **Output Attribute** list.</span></span>  
  
 <span data-ttu-id="ea2f9-110">Der Bereich **Variablen** vergleicht die beiden Ergebnisse, die Sie bei der Bereitstellung von Attributen oder Variablen ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-110">The **Variables** pane compares the two outcomes that you chose in terms of contributing attributes, or variables.</span></span> <span data-ttu-id="ea2f9-111">Die farbigen Leisten stellen visuell dar, wie stark sich die Variable auf die Zielergebnisse auswirkt.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-111">The colored bars visually represent how strongly the variable affects the target outcomes.</span></span> <span data-ttu-id="ea2f9-112">Sie können auch Liftergebnisse für die Variablen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-112">You can also view lift scores for the variables.</span></span> <span data-ttu-id="ea2f9-113">Ein Liftergebnis wird abhängig vom verwendeten Miningmodelltyp unterschiedlich berechnet, gibt jedoch i. d. R. Aufschluss über die Verbesserung im Modell, die beim Verwenden dieses Attributs für die Vorhersage erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-113">A lift score is calculated differently depending on which mining model type you are using, but generally tells you the improvement in the model when using this attribute for prediction.</span></span>  
  
 <span data-ttu-id="ea2f9-114">Im **Eingabe** Bereich können Sie dem Modell Einflussfaktoren hinzufügen, um verschiedene was-wäre-wenn-Szenarios auszuprobieren.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-114">The **Input** pane lets you add influencers to the model to try out various what-if scenarios.</span></span>  
  
### <a name="using-the-output-pane"></a><span data-ttu-id="ea2f9-115">Verwenden des Ausgabebereichs</span><span class="sxs-lookup"><span data-stu-id="ea2f9-115">Using the Output Pane</span></span>  
 <span data-ttu-id="ea2f9-116">In diesem Modell soll zuerst der Einfluss verschiedener Faktoren auf die Dienstqualität dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-116">In this initial model, you are interested in seeing how various factors affect the grade of service.</span></span> <span data-ttu-id="ea2f9-117">Zu diesem Zweck können Sie die Dienst Qualität in der Liste der Ausgabe Attribute auswählen und anschließend verschiedene Dienst Ebenen vergleichen, indem Sie Bereiche in den Dropdown Listen für **Wert 1** und **Wert 2**auswählen.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-117">To do this, you can select Service Grade from the list of output attributes, and then compare different levels of service by selecting ranges from the dropdown lists for **Value 1** and **Value 2**.</span></span>  
  
##### <a name="to-compare-lowest-and-highest-service-grades"></a><span data-ttu-id="ea2f9-118">So vergleichen Sie die niedrigste und die höchste Dienstqualität</span><span class="sxs-lookup"><span data-stu-id="ea2f9-118">To compare lowest and highest service grades</span></span>  
  
1.  <span data-ttu-id="ea2f9-119">Wählen Sie für **Wert 1**den Bereich mit den niedrigsten Werten aus.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-119">For **Value 1**, select the range with the lowest values.</span></span> <span data-ttu-id="ea2f9-120">Zum Beispiel stellt der Bereich 0-0-0,7 die niedrigsten Abbruchraten dar und damit die bestmögliche Dienstqualität.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-120">For example, the range 0-0-0.7 represents the lowest abandon rates, and therefore the best level of service.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ea2f9-121">Die genauen Werte in diesem Bereich variieren ggf. abhängig davon, wie Sie das Modell konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-121">The exact values in this range may vary depending on how you configured the model.</span></span>  
  
2.  <span data-ttu-id="ea2f9-122">Wählen Sie für **Wert 2**den Bereich mit den höchsten Werten aus.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-122">For **Value 2**, select the range with the highest values.</span></span> <span data-ttu-id="ea2f9-123">Beispielsweise steht der Bereich mit dem Wert >= 0,12 für die höchsten Abbruchraten und somit für die schlechteste Dienst Qualität.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-123">For example, the range with the value >=0.12 represents the highest abandon rates, and therefore the worst service grade.</span></span> <span data-ttu-id="ea2f9-124">Der Wert bedeutet, dass 12% der eingehenden Kundenanrufe während dieser Schicht nicht durchgestellt werden konnten und der Kunde wieder aufgelegt hat.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-124">In other words, 12% of the customers who phoned during this shift hung up before speaking to a representative.</span></span>  
  
     <span data-ttu-id="ea2f9-125">Der Inhalt des Bereichs **Variablen** wird aktualisiert, um Attribute zu vergleichen, die zu den Ergebnis Werten beitragen.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-125">The contents of the **Variables** pane are updated to compare attributes that contribute to the outcome values.</span></span> <span data-ttu-id="ea2f9-126">Die linke Spalte zeigt die Attribute an, die der besten Dienstqualität zugeordnet sind, und die rechte Spalte die Attribute für die schlechteste Dienstqualität.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-126">Therefore, the left column shows you the attributes that are associated with the best grade of service, and the right column shows you the attributes associated with the worst grade of service.</span></span>  
  
### <a name="using-the-variables-pane"></a><span data-ttu-id="ea2f9-127">Verwenden des Variablenbereichs</span><span class="sxs-lookup"><span data-stu-id="ea2f9-127">Using the Variables Pane</span></span>  
 <span data-ttu-id="ea2f9-128">In diesem Modell `Average Time Per Issue` ist es ein wichtiger Faktor.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-128">In this model, it appears that `Average Time Per Issue` is an important factor.</span></span> <span data-ttu-id="ea2f9-129">Diese Variable gibt die durchschnittliche Zeit an, nach der ein Aufruf beantwortet wird, unabhängig vom Anruftyp.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-129">This variable indicates the average time that it takes for a call to be answered, regardless of call type.</span></span>  
  
##### <a name="to-view-and-copy-probability-and-lift-scores-for-an-attribute"></a><span data-ttu-id="ea2f9-130">So können Sie Wahrscheinlichkeits- und Liftergebnisse für ein Attribut anzeigen und kopieren</span><span class="sxs-lookup"><span data-stu-id="ea2f9-130">To view and copy probability and lift scores for an attribute</span></span>  
  
1.  <span data-ttu-id="ea2f9-131">Bewegen Sie den Mauszeiger im Bereich **Variablen** über die farbige Leiste in der ersten Zeile.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-131">In the **Variables** pane, pause the mouse over the colored bar in the first row.</span></span>  
  
     <span data-ttu-id="ea2f9-132">Diese farbige Leiste zeigt, wie stark zur `Average Time Per Issue` Dienst Qualität beiträgt.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-132">This colored bar shows you how strongly `Average Time Per Issue` contributes toward the service grade.</span></span> <span data-ttu-id="ea2f9-133">Die QuickInfo zeigt das Gesamtergebnis, die Wahrscheinlichkeiten und die Liftergebnisse für jede Kombination einer Variablen mit einem Zielergebnis an.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-133">The tooltip shows an overall score, probabilities, and lift scores for each combination of a variable and a target outcome.</span></span>  
  
2.  <span data-ttu-id="ea2f9-134">Klicken Sie im Bereich **Variablen** mit der rechten Maustaste auf eine farbige Leiste, und wählen Sie **Kopieren**aus.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-134">In the **Variables** pane, right-click any colored bar and select **Copy**.</span></span>  
  
3.  <span data-ttu-id="ea2f9-135">Klicken Sie in einem Excel-Arbeitsblatt mit der rechten Maustaste auf eine Zelle, und wählen Sie **Einfügen**aus.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-135">In an Excel worksheet, right-click any cell and select **Paste**.</span></span>  
  
     <span data-ttu-id="ea2f9-136">Der Bericht wird als HTML-Tabelle eingefügt und zeigt nur die Ergebnisse für jede Leiste an.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-136">The report is pasted as an HTML table, and shows only the scores for each bar.</span></span>  
  
4.  <span data-ttu-id="ea2f9-137">Klicken Sie in einem anderen Excel-Arbeitsblatt mit der rechten Maustaste auf eine beliebige Zelle, und wählen Sie **spezielle einfügen**</span><span class="sxs-lookup"><span data-stu-id="ea2f9-137">In a different Excel worksheet, right-click any cell and select **Paste Special**.</span></span>  
  
     <span data-ttu-id="ea2f9-138">Der Bericht wird im Textformat eingefügt und enthält die verwandten Statistiken, die im nächsten Abschnitt beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-138">The report is pasted as text format, and includes the related statistics described in the next section.</span></span>  
  
### <a name="using-the-input-pane"></a><span data-ttu-id="ea2f9-139">Verwenden des Eingabebereichs</span><span class="sxs-lookup"><span data-stu-id="ea2f9-139">Using the Input Pane</span></span>  
 <span data-ttu-id="ea2f9-140">Angenommen, Sie interessieren sich für die Auswirkungen eines bestimmten Faktors, z. B. für die Schicht oder die Anzahl der Telefonisten.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-140">Suppose that you are interested in looking at the effect of a particular factor, such as the shift, or number of operators.</span></span> <span data-ttu-id="ea2f9-141">Sie können eine bestimmte Variable mithilfe des **Eingabe** Bereichs auswählen. der Bereich **Variablen** wird automatisch aktualisiert, um die beiden zuvor ausgewählten Gruppen mit der angegebenen Variablen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-141">You can select a particular variable by using the **Input** pane, and the **Variables** pane is automatically updated to compare the two previously selected groups given the specified variable.</span></span>  
  
##### <a name="to-review-the-effect-on-service-grade-by-changing-input-attributes"></a><span data-ttu-id="ea2f9-142">So überprüfen Sie die Auswirkungen auf die Dienstqualität beim Ändern von Eingabeattributen</span><span class="sxs-lookup"><span data-stu-id="ea2f9-142">To review the effect on service grade by changing input attributes</span></span>  
  
1.  <span data-ttu-id="ea2f9-143">Wählen Sie im Bereich **Eingabe** für **Attribut**die Option Shift aus.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-143">In the **Input** pane, for **attribute**, select Shift.</span></span>  
  
2.  <span data-ttu-id="ea2f9-144">Wählen Sie für **Wert**die Option **am**aus.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-144">For **Value**, select **AM**.</span></span>  
  
     <span data-ttu-id="ea2f9-145">Der Bereich **Variablen** wird aktualisiert, um die Auswirkungen auf das Modell anzuzeigen, wenn die UMSCHALTTASTE **am**ist.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-145">The **Variables** pane updates to show the impact on the model when the shift is **AM**.</span></span> <span data-ttu-id="ea2f9-146">Alle anderen Auswahlen bleiben unverändert, und Sie vergleichen immer noch die niedrigsten und höchsten Dienst Qualitäten.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-146">All other selections remain the same - you are still comparing the lowest and highest service grades.</span></span>  
  
3.  <span data-ttu-id="ea2f9-147">Wählen Sie für **Wert**die Option **PM1**aus.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-147">For **Value**, select **PM1**.</span></span>  
  
     <span data-ttu-id="ea2f9-148">Der Bereich **Variablen** wird aktualisiert, um die Auswirkungen auf das Modell anzuzeigen, wenn sich die UMSCHALTTASTE ändert.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-148">The **Variables** pane updates to show the impact on the model when the shift changes.</span></span>  
  
4.  <span data-ttu-id="ea2f9-149">Klicken Sie im Bereich **Eingabe** unter **Attribut**auf die nächste leere Zeile, und wählen Sie dann Anrufe aus.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-149">In the **Input** pane, click the next blank row under **Attribute**, and select Calls.</span></span> <span data-ttu-id="ea2f9-150">Wählen Sie für **Wert**den Bereich aus, der die größte Anzahl von Aufrufen angibt.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-150">For **Value**, select the range that indicates the greatest number of calls.</span></span>  
  
     <span data-ttu-id="ea2f9-151">Der Liste wird eine neue Eingabebedingung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-151">A new input condition is added to the list.</span></span> <span data-ttu-id="ea2f9-152">Der Bereich **Variablen** wird aktualisiert, um die Auswirkungen auf das Modell für eine bestimmte Schicht anzuzeigen, wenn das aufrufvolume am höchsten ist.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-152">The **Variables** pane updates to show the impact on the model for a particular shift when the call volume is highest.</span></span>  
  
5.  <span data-ttu-id="ea2f9-153">Ändern Sie weiter die Werte für Schicht und Anrufe, um ein genaues Bild der Wechselwirkungen zwischen den Werten für Schicht, Anrufaufkommen und Dienstqualität zu bekommen.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-153">Continue to change the values for Shift and Calls to find any interesting correlations between shift, call volume, and service grade.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ea2f9-154">Wenn Sie den **Eingabe** Bereich löschen möchten, sodass Sie unterschiedliche Attribute verwenden können, klicken Sie auf **Viewer-Inhalt aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-154">To clear the **Input** pane so that you can use different attributes, click **Refresh viewer content**.</span></span>  
  
### <a name="interpreting-the-statistics-provided-in-the-viewer"></a><span data-ttu-id="ea2f9-155">Interpretieren der im Viewer bereitgestellten Statistiken</span><span class="sxs-lookup"><span data-stu-id="ea2f9-155">Interpreting the Statistics Provided in the Viewer</span></span>  
 <span data-ttu-id="ea2f9-156">Längere Wartezeiten sind ein wesentlicher Vorhersagefaktor für eine hohe Abbruchrate und bedeuten eine schlechte Dienstqualität.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-156">Longer waiting times are a strong predictor of a high abandon rate, meaning a poor service grade.</span></span> <span data-ttu-id="ea2f9-157">Diese Schlussfolgerung scheint zunächst offensichtlich. Das Miningmodell stellt Ihnen jedoch einige zusätzliche statistische Daten bereit, mit denen Sie diese Trends umfassender interpretieren können.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-157">This may seem an obvious conclusion; however, the mining model provides you with some additional statistical data to help you interpret these trends.</span></span>  
  
-   <span data-ttu-id="ea2f9-158">**Score**: Wert, der die Gesamt Wichtigkeit dieser Variablen für die Unterscheidung Zwischenergebnissen angibt.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-158">**Score**: Value that indicates the overall importance of this variable for discriminating between outcomes.</span></span> <span data-ttu-id="ea2f9-159">Je höher das Ergebnis, desto stärker wirkt sich die Variable auf das Ergebnis aus.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-159">The higher the score, the stronger the effect the variable has on the outcome.</span></span>  
  
-   <span data-ttu-id="ea2f9-160">**Wahrscheinlichkeit von Wert 1**: Prozentsatz, der die Wahrscheinlichkeit dieses Werts für dieses Ergebnis darstellt.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-160">**Probability of value 1**: Percentage that represents the probability of this value for this outcome.</span></span>  
  
-   <span data-ttu-id="ea2f9-161">**Wahrscheinlichkeit von Wert 2**: Prozentsatz, der die Wahrscheinlichkeit dieses Werts für dieses Ergebnis darstellt.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-161">**Probability of value 2**: Percentage that represents the probability of this value for this outcome.</span></span>  
  
-   <span data-ttu-id="ea2f9-162">**Lift für Wert 1** und **Lift für Wert 2**: Bewertungen, die die Auswirkung der Verwendung dieser speziellen Variablen auf die Vorhersage von Wert 1 und Wert 2 darstellen.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-162">**Lift for Value 1** and **Lift for Value 2**: Scores that represents the impact of using this particular variable for predicting the Value 1 and Value 2 outcomes.</span></span> <span data-ttu-id="ea2f9-163">Je höher das Ergebnis, desto besser sind die Ergebnisse, die mit dieser Variablen ermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-163">The higher the score, the better the variable is at predicting the outcomes.</span></span>  
  
 <span data-ttu-id="ea2f9-164">Die folgende Tabelle enthält einige Beispielwerte für die wichtigsten Einflussfaktoren.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-164">The following table contains some example values for the top influencers.</span></span> <span data-ttu-id="ea2f9-165">Beispielsweise ist die **Wahrscheinlichkeit von Wert 1** 60,6%, und die **Wahrscheinlichkeit von Wert 2** beträgt 8,30%. Dies bedeutet, dass bei einer durchschnittlichen Zeit pro Problem im Bereich von 44-70 Minuten 60,6% der Fälle in der Schicht mit den höchsten Dienst Qualitäten (Wert 1) und 8,30% der Fälle in der Schicht mit den schlechteren Dienst Qualitäten (Wert 2) waren.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-165">For example, the **Probability of value 1** is 60.6% and **Probability of value 2** is 8.30%, meaning that when the Average Time Per Issue was in the range of 44-70 minutes, 60.6% of cases were in the shift with the highest service grades (Value 1), and 8.30% of cases were in the shift with the worse service grades (Value 2).</span></span>  
  
 <span data-ttu-id="ea2f9-166">Aus diesen Informationen lassen sich mehrere Schlussfolgerungen ableiten.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-166">From this information, you can draw some conclusions.</span></span> <span data-ttu-id="ea2f9-167">Kürzere Antwortzeiten (der Bereich von 44-70) wirken sich sehr stark auf eine bessere Dienstqualität (der Bereich 0,00-0,07) aus.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-167">Shorter call response time (the range of 44-70) strongly influences better service grade (the range 0.00-0.07).</span></span> <span data-ttu-id="ea2f9-168">Das Ergebnis (92,35) besagt, dass diese Variable sehr wichtig ist.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-168">The score (92.35) tells you that this variable is very important.</span></span>  
  
 <span data-ttu-id="ea2f9-169">Wenn Sie jedoch die Liste der Faktoren genauer überprüfen, finden Sie einige andere Faktoren, die weniger deutliche Auswirkungen haben und schwieriger zu interpretieren sind.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-169">However, as you look down the list of contributing factors, you see some other factors with effects that are more subtle and more difficult to interpret.</span></span> <span data-ttu-id="ea2f9-170">Zum Beispiel scheint die Schicht die Dienstqualität zu beeinflussen, aber das Liftergebnis und die relativen Wahrscheinlichkeiten geben an, dass die Schicht kein Hauptfaktor ist.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-170">For example, shift appears to influence service, but the lift scores and the relative probabilities indicate that shift is not a major factor.</span></span>  
  
|<span data-ttu-id="ea2f9-171">attribute</span><span class="sxs-lookup"><span data-stu-id="ea2f9-171">Attribute</span></span>|<span data-ttu-id="ea2f9-172">Wert</span><span class="sxs-lookup"><span data-stu-id="ea2f9-172">Value</span></span>|<span data-ttu-id="ea2f9-173">Begünstigt \< 0,07</span><span class="sxs-lookup"><span data-stu-id="ea2f9-173">Favors \< 0.07</span></span>|<span data-ttu-id="ea2f9-174">Begünstigt >= 0,12</span><span class="sxs-lookup"><span data-stu-id="ea2f9-174">Favors >= 0.12</span></span>|  
|---------------|-----------|--------------------|----------------------|  
|<span data-ttu-id="ea2f9-175">Average Time Per Issue</span><span class="sxs-lookup"><span data-stu-id="ea2f9-175">Average Time Per Issue</span></span>|<span data-ttu-id="ea2f9-176">89,087-120,000</span><span class="sxs-lookup"><span data-stu-id="ea2f9-176">89.087 - 120.000</span></span>||<span data-ttu-id="ea2f9-177">Ergebnis: 100</span><span class="sxs-lookup"><span data-stu-id="ea2f9-177">Score:  100</span></span><br /><br /> <span data-ttu-id="ea2f9-178">Wahrscheinlichkeit von value1:4,45%</span><span class="sxs-lookup"><span data-stu-id="ea2f9-178">Probability of Value1: 4.45 %</span></span><br /><br /> <span data-ttu-id="ea2f9-179">Wahrscheinlichkeit von Value2:51,94%</span><span class="sxs-lookup"><span data-stu-id="ea2f9-179">Probability of Value2: 51.94 %</span></span><br /><br /> <span data-ttu-id="ea2f9-180">Lift für value1:0,19</span><span class="sxs-lookup"><span data-stu-id="ea2f9-180">Lift for Value1: 0.19</span></span><br /><br /> <span data-ttu-id="ea2f9-181">Lift für Value2:1,94</span><span class="sxs-lookup"><span data-stu-id="ea2f9-181">Lift for Value2: 1.94</span></span>|  
|<span data-ttu-id="ea2f9-182">Average Time Per Issue</span><span class="sxs-lookup"><span data-stu-id="ea2f9-182">Average Time Per Issue</span></span>|<span data-ttu-id="ea2f9-183">44,000-70,597</span><span class="sxs-lookup"><span data-stu-id="ea2f9-183">44.000 - 70.597</span></span>|<span data-ttu-id="ea2f9-184">Ergebnis: 92,35</span><span class="sxs-lookup"><span data-stu-id="ea2f9-184">Score: 92.35</span></span><br /><br /> <span data-ttu-id="ea2f9-185">Wahrscheinlichkeit von Wert 1: 60,06 %</span><span class="sxs-lookup"><span data-stu-id="ea2f9-185">Probability of Value1: 60.06 %</span></span><br /><br /> <span data-ttu-id="ea2f9-186">Wahrscheinlichkeit von Wert 2: 8,30 %</span><span class="sxs-lookup"><span data-stu-id="ea2f9-186">Probability of Value2: 8.30 %</span></span><br /><br /> <span data-ttu-id="ea2f9-187">Lift für Wert 1: 2,61</span><span class="sxs-lookup"><span data-stu-id="ea2f9-187">Lift for Value1: 2.61</span></span><br /><br /> <span data-ttu-id="ea2f9-188">Lift für Wert 2: 0,31</span><span class="sxs-lookup"><span data-stu-id="ea2f9-188">Lift for Value2: 0.31</span></span>||  
  
 [<span data-ttu-id="ea2f9-189">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="ea2f9-189">Back to Top</span></span>](#bkmk_NNviewer)  
  
##  <a name="microsoft-generic-content-tree-viewer"></a><a name="bkmk_genviewer"></a><span data-ttu-id="ea2f9-190">Microsoft Generic Content Tree-Viewer</span><span class="sxs-lookup"><span data-stu-id="ea2f9-190">Microsoft Generic Content Tree Viewer</span></span>  
 <span data-ttu-id="ea2f9-191">Mit diesem Viewer können Sie die vom Algorithmus bei der Modellverarbeitung erstellten Informationen noch ausführlicher untersuchen.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-191">This viewer can be used to view even more detailed information created by the algorithm when the model is processed.</span></span> <span data-ttu-id="ea2f9-192">Der **microsoftgeneric Content Tree Viewer** stellt das Mining Modell als eine Reihe von Knoten dar, in denen jeder Knoten gelernte Informationen über die Trainingsdaten repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-192">The **MicrosoftGeneric Content Tree Viewer** represents the mining model as a series of nodes, wherein each node represents learned knowledge about the training data.</span></span> <span data-ttu-id="ea2f9-193">Dieser Viewer kann mit allen Modellen verwendet werden, die Inhalte der Knoten variieren jedoch abhängig vom Modelltyp.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-193">This viewer can be used with all models, but the contents of the nodes are different depending in the model type.</span></span>  
  
 <span data-ttu-id="ea2f9-194">Bei neuronalen Netzwerkmodellen oder logistischen Regressionsmodellen kann z. B. der `marginal statistics node` sehr nützlich sein.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-194">For neural network models or logistic regression models, you might find the `marginal statistics node` particularly useful.</span></span> <span data-ttu-id="ea2f9-195">Dieser Knoten enthält abgeleitete Statistiken über die Werteverteilung in den Daten.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-195">This node contains derived statistics about the distribution of values in your data.</span></span> <span data-ttu-id="ea2f9-196">Diese Informationen können nützlich sein, um ohne die Ausführung vieler T-SQL-Abfragen schnell eine Zusammenfassung der Daten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-196">This information can be useful if you want to get a summary of the data without having to write many T-SQL queries.</span></span> <span data-ttu-id="ea2f9-197">Das Diagramm mit Klassifizierungswerten im vorherigen Thema wurde aus dem Knoten für Randstatistiken abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-197">The chart of binning values in the previous topic was derived from the marginal statistics node.</span></span>  
  
#### <a name="to-obtain-a-summary-of-data-values-from-the-mining-model"></a><span data-ttu-id="ea2f9-198">So rufen Sie eine Zusammenfassung der Datenwerte aus dem Miningmodell ab</span><span class="sxs-lookup"><span data-stu-id="ea2f9-198">To obtain a summary of data values from the mining model</span></span>  
  
1.  <span data-ttu-id="ea2f9-199">Wählen Sie im Data Mining-Designer auf der Registerkarte **Mining Modell-Viewer** aus \<mining model name> .</span><span class="sxs-lookup"><span data-stu-id="ea2f9-199">In Data Mining Designer, in the **Mining Model Viewer** tab, select \<mining model name>.</span></span>  
  
2.  <span data-ttu-id="ea2f9-200">Wählen Sie in der Liste **Viewer** den Bereich **Microsoft Generic Content Tree Viewer**aus.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-200">From the **Viewer** list, select **Microsoft Generic Content Tree Viewer**.</span></span>  
  
     <span data-ttu-id="ea2f9-201">Die Ansicht des Miningmodells wird aktualisiert und zeigt im linken Bereich eine Knotenhierarchie und im rechten Bereich eine HTML-Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-201">The view of the mining model refreshes to show a node hierarchy in the left-hand pane and an HTML table in the right-hand pane.</span></span>  
  
3.  <span data-ttu-id="ea2f9-202">Klicken Sie im Bereich **Knoten Beschriftung** auf den Knoten mit dem Namen 10000000000000000.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-202">In the **Node Caption** pane, click the node that has the name 10000000000000000.</span></span>  
  
     <span data-ttu-id="ea2f9-203">Der oberste Knoten in jedem Modell ist immer der Modellstammknoten.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-203">The topmost node in any model is always the model root node.</span></span> <span data-ttu-id="ea2f9-204">In einem neuronalen Netzwerk oder logistischen Regressionsmodell ist der Knoten direkt unter diesem der Knoten für Randstatistiken.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-204">In a neural network or logistic regression model, the node immediately under that is the marginal statistics node.</span></span>  
  
4.  <span data-ttu-id="ea2f9-205">Scrollen Sie im Bereich " **Knoten Details** " nach unten, bis Sie die Zeile NODE_DISTRIBUTION finden.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-205">In the **Node Details** pane, scroll down until you find the row, NODE_DISTRIBUTION.</span></span>  
  
5.  <span data-ttu-id="ea2f9-206">Führen Sie einen Bildlauf nach unten bis zur Tabelle NODE_DISTRIBUTION durch, um die Werteverteilung anzuzeigen, die vom Neural Network-Algorithmus berechnet wurde.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-206">Scroll down through the NODE_DISTRIBUTION table to view the distribution of values as calculated by the neural network algorithm.</span></span>  
  
 <span data-ttu-id="ea2f9-207">Wenn Sie diese Daten in einem Bericht verwenden möchten, können Sie die Informationen für bestimmte Zeilen auswählen und anschließend kopieren, oder Sie können mit der folgenden DMX-Abfrage (Data Mining Extensions) den gesamten Inhalt des Knotens extrahieren.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-207">To use this data in a report, you could select and then copy the information for specific rows, or you can use the following Data Mining Extensions (DMX) query to extract the complete contents of the node.</span></span>  
  
```  
SELECT *   
FROM [Call Center EQ4].CONTENT  
WHERE NODE_NAME = '10000000000000000'  
```  
  
 <span data-ttu-id="ea2f9-208">Sie können auch die Knotenhierarchie und die Details in der Tabelle NODE_DISTRIBUTION verwenden, um einzelne Pfade im neuronalen Netzwerk zu durchlaufen und Statistiken in der verborgenen Ebene anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ea2f9-208">You can also use the node hierarchy and the details in the NODE_DISTRIBUTION table to traverse individual paths in the neural network and view statistics from the hidden layer.</span></span> <span data-ttu-id="ea2f9-209">Weitere Informationen finden Sie unter [Beispiele für neuronale Netzwerkmodell Abfragen](../../2014/analysis-services/data-mining/neural-network-model-query-examples.md).</span><span class="sxs-lookup"><span data-stu-id="ea2f9-209">For more information, see [Neural Network Model Query Examples](../../2014/analysis-services/data-mining/neural-network-model-query-examples.md).</span></span>  
  
 [<span data-ttu-id="ea2f9-210">Zurück zum Anfang</span><span class="sxs-lookup"><span data-stu-id="ea2f9-210">Back to Top</span></span>](#bkmk_NNviewer)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="ea2f9-211">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="ea2f9-211">Next Task in Lesson</span></span>  
 [<span data-ttu-id="ea2f9-212">Hinzufügen eines logistischen Regressionsmodells zur Callcenterstruktur &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="ea2f9-212">Adding a Logistic Regression Model to the Call Center Structure &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/add-logistic-regression-model-to-call-center-intermediate-data-mining.md)  
  
## <a name="see-also"></a><span data-ttu-id="ea2f9-213">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ea2f9-213">See Also</span></span>  
 <span data-ttu-id="ea2f9-214">[Mining Modell Inhalt von neuronalen Netzwerkmodellen &#40;Analysis Services Data Mining-&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-neural-network-models-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="ea2f9-214">[Mining Model Content for Neural Network Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-model-content-for-neural-network-models-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="ea2f9-215">[Beispiele für neuronale Netzwerkmodell Abfragen](../../2014/analysis-services/data-mining/neural-network-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="ea2f9-215">[Neural Network Model Query Examples](../../2014/analysis-services/data-mining/neural-network-model-query-examples.md) </span></span>  
 <span data-ttu-id="ea2f9-216">[Technische Referenz für den Microsoft Neural Network-Algorithmus](../../2014/analysis-services/data-mining/microsoft-neural-network-algorithm-technical-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ea2f9-216">[Microsoft Neural Network Algorithm Technical Reference](../../2014/analysis-services/data-mining/microsoft-neural-network-algorithm-technical-reference.md) </span></span>  
 [<span data-ttu-id="ea2f9-217">Ändern der Diskretisierung von Spalten in Miningmodellen</span><span class="sxs-lookup"><span data-stu-id="ea2f9-217">Change the Discretization of a Column in a Mining Model</span></span>](../../2014/analysis-services/data-mining/change-the-discretization-of-a-column-in-a-mining-model.md)  
  
  