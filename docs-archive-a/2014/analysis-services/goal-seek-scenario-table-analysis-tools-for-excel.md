---
title: Zielsuchszenario (Tabellenanalyse Tools für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- scenario analysis
- goal seek scenario
ms.assetid: efe50306-cf7c-46b3-9cc4-e7f0b6968b0c
author: minewiskan
ms.author: owend
ms.openlocfilehash: b3b4df4f78a2d3652b1dac3c566e66507b523ea5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616260"
---
# <a name="goal-seek-scenario-table-analysis-tools-for-excel"></a><span data-ttu-id="75d0d-102">Zielsucheszenario (Tabellenanalysetools für Excel)</span><span class="sxs-lookup"><span data-stu-id="75d0d-102">Goal Seek Scenario (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="75d0d-103">![Zielsuche (Schaltfläche in Tabellenanalysetools)](media/tat-goalseek.gif "Zielsuche (Schaltfläche in Tabellenanalysetools)")</span><span class="sxs-lookup"><span data-stu-id="75d0d-103">![Goal Seek button in Table Analysis tools](media/tat-goalseek.gif "Goal Seek button in Table Analysis tools")</span></span>  
  
 <span data-ttu-id="75d0d-104">Das Tool " **zielsuchszenario** " ist eine Ergänzung zum [What if](what-if-scenario-table-analysis-tools-for-excel.md) Scenario-Tool.</span><span class="sxs-lookup"><span data-stu-id="75d0d-104">The **Goal Seek** scenario tool is complementary to the [What If](what-if-scenario-table-analysis-tools-for-excel.md) scenario tool.</span></span> <span data-ttu-id="75d0d-105">Das **Was-wäre-wenn-** Tool informiert Sie über die Auswirkungen einer Änderung, während das Tool " **Zielsuche** " die zugrunde liegenden Faktoren anzeigt, die geändert werden müssen, um ein gewünschtes Ergebnis zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="75d0d-105">The **What-If** tool tells you the impact of making a change, whereas the **Goal Seek** tool tells you the underlying factors that must change to achieve a desired result.</span></span>  
  
 <span data-ttu-id="75d0d-106">Nehmen wir beispielsweise an, Sie möchten die Kundenzufriedenheit steigern.</span><span class="sxs-lookup"><span data-stu-id="75d0d-106">For example, let's say your goal is to increase customer satisfaction.</span></span> <span data-ttu-id="75d0d-107">Mithilfe der **Zielsuche** können Sie feststellen, welche Faktoren die Kundenzufriedenheit am wahrscheinlichsten steigern und entscheiden, ob diese Änderungen kostengünstig sind.</span><span class="sxs-lookup"><span data-stu-id="75d0d-107">You can use **Goal Seek** analysis to determine which factors would be most likely to increase customer satisfaction, and decide whether those changes are cost-effective.</span></span>  
  
 <span data-ttu-id="75d0d-108">Nach Abschluss der Analyse durch das Tool werden zwei neue Spalten in der Quelldatentabelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="75d0d-108">When the tool finishes its analysis, it creates two new columns in the source data table.</span></span> <span data-ttu-id="75d0d-109">Diese Spalten zeigen die *Wahrscheinlichkeit* , dass das Zielergebnis erreicht werden kann, und ggf. die empfohlene Änderung an.</span><span class="sxs-lookup"><span data-stu-id="75d0d-109">These columns show the *likelihood* that the targeted outcome can be achieved, and the recommended change, if any.</span></span>  
  
 <span data-ttu-id="75d0d-110">Das Tool kann ein Dataset analysieren und Voraussagen für den gesamten Satz treffen, oder Sie können die Analyse erstellen und dann Szenarios einzeln testen.</span><span class="sxs-lookup"><span data-stu-id="75d0d-110">The tool can analyze a set of data and make predictions for the entire set, or you can create the analysis and then test scenarios one at a time.</span></span>  
  
## <a name="using-the-goal-seek-scenario-tool"></a><span data-ttu-id="75d0d-111">Verwenden des Zielsucheszenario-Tools</span><span class="sxs-lookup"><span data-stu-id="75d0d-111">Using the Goal Seek Scenario Tool</span></span>  
  
1.  <span data-ttu-id="75d0d-112">Öffnen Sie eine Excel-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="75d0d-112">Open an Excel table.</span></span>  
  
2.  <span data-ttu-id="75d0d-113">Klicken Sie auf **Szenarien**, und wählen Sie **Zielsuche**aus.</span><span class="sxs-lookup"><span data-stu-id="75d0d-113">Click **Scenarios**, and select **Goal Seek**.</span></span>  
  
3.  <span data-ttu-id="75d0d-114">Wählen Sie im Dialogfeld **Szenarienanalyse: Zielsuche** in der Liste die Spalte aus, die den Zielwert enthält.</span><span class="sxs-lookup"><span data-stu-id="75d0d-114">In the **Scenario Analysis: Goal Seek** dialog box, select the column that contains the target value from the list.</span></span>  
  
4.  <span data-ttu-id="75d0d-115">Geben Sie den Wert an, den Sie erzielen möchten.</span><span class="sxs-lookup"><span data-stu-id="75d0d-115">Specify the value that you want to achieve.</span></span>  
  
     <span data-ttu-id="75d0d-116">Wenn das Spaltenziel fortlaufende numerische Werte enthält, können Sie auch eine gewünschte Zunahme oder Abnahme des Werts angeben.</span><span class="sxs-lookup"><span data-stu-id="75d0d-116">If the column goal contains continuous numeric values, you can also specify a desired increase or decrease in the value.</span></span> <span data-ttu-id="75d0d-117">Beispielsweise können Sie **Sales** als Spalte auswählen und angeben, dass das Ziel eine Erhöhung von 120% ist.</span><span class="sxs-lookup"><span data-stu-id="75d0d-117">For example, you might choose **Sales** as the column and specify that the target is an increase of 120%.</span></span>  
  
     <span data-ttu-id="75d0d-118">Sie können das Ziel auch als Wertebereich angeben, indem Sie eine Unter- und Obergrenze angeben.</span><span class="sxs-lookup"><span data-stu-id="75d0d-118">Or, you can specify the goal as a range of values, by typing a lower and upper limit.</span></span>  
  
5.  <span data-ttu-id="75d0d-119">Geben Sie die Spalte an, die die Werte enthält, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="75d0d-119">Specify the column that contains the values you will change.</span></span> <span data-ttu-id="75d0d-120">Wählen Sie mit anderen Worten die Spalte aus, die bearbeitet werden muss, um das gewünschte Ergebnis zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="75d0d-120">In other words, pick the column that will be manipulated to produce the desired result.</span></span>  
  
6.  <span data-ttu-id="75d0d-121">Klicken Sie optional auf **Spalten auswählen, die für die Analyse verwendet werden**sollen, und wählen Sie Spalten aus, die nützliche Informationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="75d0d-121">Optionally, click **Choose columns to be used for analysis**, and select columns that contain useful information.</span></span> <span data-ttu-id="75d0d-122">Heben Sie die Auswahl der Spalten auf, die nicht zur Analyse beitragen.</span><span class="sxs-lookup"><span data-stu-id="75d0d-122">Deselect columns that will not contribute to the analysis.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="75d0d-123">Heben Sie die Auswahl nicht für Spalten auf, die Sie entweder für das Ziel oder die Änderung verwenden.</span><span class="sxs-lookup"><span data-stu-id="75d0d-123">Do not deselect columns that you will use for either the goal or the change.</span></span> <span data-ttu-id="75d0d-124">Diese Spalten sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="75d0d-124">These columns are required.</span></span>  
  
7.  <span data-ttu-id="75d0d-125">Geben Sie an, ob Sie Vorhersagen für die gesamte Tabelle oder nur für die ausgewählten Ziele erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="75d0d-125">Specify whether you want to make predictions for the entire table, or for only the selected row.</span></span>  
  
8.  <span data-ttu-id="75d0d-126">Wenn Sie die **gesamte Tabellen** Option ausgewählt haben, fügt das Tool die Vorhersagen der Quell Tabelle in zwei neue Spalten hinzu.</span><span class="sxs-lookup"><span data-stu-id="75d0d-126">If you selected the **Entire table** option, the tool adds the predictions to the source table in two new columns.</span></span>  
  
9. <span data-ttu-id="75d0d-127">Wenn Sie die Option **in dieser Zeile**ausgewählt haben, werden die Ergebnisse der Analyse im Dialogfeld zur Überprüfung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="75d0d-127">If you selected the option **On this row**, the results of analysis are output to the dialog box for review.</span></span> <span data-ttu-id="75d0d-128">Das Dialogfeld bleibt geöffnet, damit Sie damit fortfahren können, andere Werte und Ziele auszuprobieren.</span><span class="sxs-lookup"><span data-stu-id="75d0d-128">The dialog box stays open so that you can continue trying out different values and goals.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="75d0d-129">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="75d0d-129">Requirements</span></span>  
 <span data-ttu-id="75d0d-130">Für dieses Tool wird der Microsoft Logistic Regression-Algorithmus verwendet, der numerische oder diskrete Werte verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="75d0d-130">This tool uses the Microsoft Logistic Regression algorithm, which can process either numeric or discrete values.</span></span>  
  
 <span data-ttu-id="75d0d-131">Sie können die Vorhersage mehrere Male ausführen und zu einem späteren Zeitpunkt andere Spalten auswählen. Es muss jedoch jede Kombination aus Ziel und Änderung separat berechnet werden.</span><span class="sxs-lookup"><span data-stu-id="75d0d-131">You can run the prediction multiple times, and select different columns later, but each combination of a goal and a change must be calculated separately.</span></span>  
  
 <span data-ttu-id="75d0d-132">Sie erzielen bessere Ergebnisse, wenn Sie Spalten zur Analyse auswählen, die nützliche Informationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="75d0d-132">You can achieve better results if you select columns for analysis that contain useful information.</span></span> <span data-ttu-id="75d0d-133">Wenn Sie jedoch zu wenige Spalten einbeziehen, ist es u. U. schwierig, ein Ergebnis zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="75d0d-133">However, if you include too few columns, it might be difficult to obtain a result.</span></span>  
  
 <span data-ttu-id="75d0d-134">Stellen Sie beim Erstellen von Vorhersagen sicher, dass Sie eine Zeile auswählen, die nicht bereits das gewünschte Ergebnis enthält, andernfalls erhalten Sie einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="75d0d-134">When you create predictions one at a time, be sure to select a row that does not already contain the desired result, or you may get an error.</span></span> <span data-ttu-id="75d0d-135">Mit anderen Worten: Wenn der Zweck einer Zielsuche ist, begünstigende Faktoren für einen Fahrradkauf zu ermitteln, sollten nur Kunden einbezogen werden, die noch kein Fahrrad gekauft haben.</span><span class="sxs-lookup"><span data-stu-id="75d0d-135">In other words, if the purpose of goal seeking is to determine factors that encourage bike purchases, you should only include customers who did not purchase a bike.</span></span>  
  
## <a name="understanding-the-results-of-goal-seek-analysis"></a><span data-ttu-id="75d0d-136">Grundlegendes zu den Ergebnissen der Zielsucheanalyse</span><span class="sxs-lookup"><span data-stu-id="75d0d-136">Understanding the Results of Goal Seek Analysis</span></span>  
 <span data-ttu-id="75d0d-137">Beim Erstellen eines Zielsucheszenarios werden vom Tool die folgenden drei Vorgänge ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="75d0d-137">When you create a goal seeking scenario, the tool does three things:</span></span>  
  
-   <span data-ttu-id="75d0d-138">Es wird eine Data Mining-Struktur erstellt, in der wichtige Fakten zu den Daten in der Tabelle gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="75d0d-138">Creates a data mining structure that stores key facts about the data in your table.</span></span>  
  
-   <span data-ttu-id="75d0d-139">Es wird anhand der Daten ein Logistic Regression-Miningmodell erstellt.</span><span class="sxs-lookup"><span data-stu-id="75d0d-139">Creates a logistic regression mining model based on the data.</span></span>  
  
-   <span data-ttu-id="75d0d-140">Es wird eine Vorhersage für jeden Wert erstellt, den Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="75d0d-140">Creates a prediction for each value that you specify.</span></span>  
  
 <span data-ttu-id="75d0d-141">Wenn Sie Zielsucheszenarios einzeln testen, können Sie die Ergebnisse interaktiv anzeigen.</span><span class="sxs-lookup"><span data-stu-id="75d0d-141">If you test goal-seeking scenarios one at a time, you can view the results interactively.</span></span> <span data-ttu-id="75d0d-142">Dies entspricht dem Erstellen einer *SINGLETON-Vorhersage Abfrage*.</span><span class="sxs-lookup"><span data-stu-id="75d0d-142">This is the same as creating a *singleton prediction query*.</span></span>  
  
 <span data-ttu-id="75d0d-143">Das Tool meldet im **Ergebnis** Bereich des Dialog Felds, ob es erfolgreich ein Szenario gefunden hat, das das gewünschte Ziel erreicht.</span><span class="sxs-lookup"><span data-stu-id="75d0d-143">The tool reports in the **Results** pane of the dialog box whether it was successful in finding a scenario that achieves the desired goal.</span></span> <span data-ttu-id="75d0d-144">Wenn eine erfolgreiche Lösung gefunden wurde, generiert das Tool auch eine Empfehlung mit der erforderlichen Änderung.</span><span class="sxs-lookup"><span data-stu-id="75d0d-144">If a successful solution was found, the tool also generates a recommendation that tells you the required change.</span></span> <span data-ttu-id="75d0d-145">Das Tool zur **Zielsuche** könnte z. b. Aufschluss darüber geben, dass die Verbindungs Distanz weniger als 5 Kilometer betragen sollte.</span><span class="sxs-lookup"><span data-stu-id="75d0d-145">For example, the **Goal Seek** tool might tell you that the commuting distance should be less than 5 miles.</span></span>  
  
 <span data-ttu-id="75d0d-146">Beispielergebnisse:</span><span class="sxs-lookup"><span data-stu-id="75d0d-146">Example results:</span></span>  
  
 <span data-ttu-id="75d0d-147">**Bei der Zielsuche für Interesse am Kauf wurde eine Lösung gefunden.**</span><span class="sxs-lookup"><span data-stu-id="75d0d-147">**Goal Seeking for Interest in Buying has found a solution.**</span></span>  
  
 <span data-ttu-id="75d0d-148">**Nächster Treffer erreicht durch Ändern von 'Entfernung zur Arbeit' in '2-5 km'.**</span><span class="sxs-lookup"><span data-stu-id="75d0d-148">**Closest match obtained by changing 'Commute distance' to '2-5 miles'.**</span></span>  
  
 <span data-ttu-id="75d0d-149">Da dieses Ergebnis auf einer vorhandenen Zeile in der Datentabelle beruht, bedeutet dies Folgendes: Wenn alle Werte dieses Kunden unverändert bleiben, aber sich der Arbeitsweg auf 2 – 5 km reduziert, ist es wahrscheinlich, dass der Kunde ein Fahrrad kauft.</span><span class="sxs-lookup"><span data-stu-id="75d0d-149">Because this result is based on an existing row in the data table, it means that, for a particular customer, if all else about the customer stayed the same but the customer's commute was reduced to 2-5 miles, the customer would be somewhat more likely buy a bicycle.</span></span>  
  
 <span data-ttu-id="75d0d-150">Wenn Sie Ziel basierte Vorhersagen für alle Zeilen in der Excel-Tabelle erstellen, indem Sie die **gesamte Tabelle**angeben, erstellt das Tool zwei neue Spalten in der ursprünglichen Datentabelle.</span><span class="sxs-lookup"><span data-stu-id="75d0d-150">If you create goal-seeking predictions for all the rows in the Excel table by specifying **Entire table**, thetool creates two new columns in the original data table.</span></span> <span data-ttu-id="75d0d-151">Die erste der Tabelle hinzugefügte Spalte enthält entweder ein Häkchen in einem grünen Kreis, was bedeutet, dass das Ziel erreicht werden kann, oder ein X in einem roten Kreis, was bedeutet, dass das Ziel durch keine Änderung erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="75d0d-151">The first column that is added to the table contains either a check mark in a green circle, to indicate that the goal can be met, or an X mark in a red circle, to indicate that no changes can be made that will enable the goal.</span></span>  
  
 <span data-ttu-id="75d0d-152">Die zweite Spalte enthält die empfohlene Änderung.</span><span class="sxs-lookup"><span data-stu-id="75d0d-152">The second column contains the recommended change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="75d0d-153">Der Vertrauensgrad der Empfehlung und ihr Erfolg sind durch den Algorithmus vorbestimmt und können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="75d0d-153">The confidence level for the recommendation and its success are predetermined by the algorithm and cannot be changed.</span></span>  
  
## <a name="related-tools"></a><span data-ttu-id="75d0d-154">Verwandte Tools</span><span class="sxs-lookup"><span data-stu-id="75d0d-154">Related Tools</span></span>  
 <span data-ttu-id="75d0d-155">Der Data Mining-Client für Excel, bei dem es sich um ein separates Add-In mit erweiterter Data Mining-Funktionalität handelt, enthält Assistenten zum Erstellen von Data Mining-Modellen, die Verhalten vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="75d0d-155">The Data Mining Client for Excel, which is a separate add-in that provides more advanced data mining functionality, includes wizards for creating data mining models that predict behavior.</span></span> <span data-ttu-id="75d0d-156">Weitere Informationen finden Sie unter [Erstellen eines Data Mining-Modells](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="75d0d-156">For more information, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>  
  
 <span data-ttu-id="75d0d-157">Weitere Informationen zum Algorithmus, der vom Tool für das Tool zur **Zielsuche** verwendet wird, finden Sie im Thema "Microsoft Logistic Regression-Algorithmus" in der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Online Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="75d0d-157">For more information about the algorithm used by the **Goal Seek** scenario tool, see the topic "Microsoft Logistic Regression Algorithm" in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75d0d-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="75d0d-158">See Also</span></span>  
 [<span data-ttu-id="75d0d-159">Tabellenanalysetools für Excel</span><span class="sxs-lookup"><span data-stu-id="75d0d-159">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)  
  
  
