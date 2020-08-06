---
title: Was-wäre-wenn-Szenario (Tabellenanalyse Tools für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- what if scenario
- scenario analysis
ms.assetid: 4df5a5c5-1983-4009-a7c5-cd340649fd2f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4bb5c5e866c1320c297fb4f2760bca58623f6601
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727149"
---
# <a name="what-if-scenario-table-analysis-tools-for-excel"></a><span data-ttu-id="627c3-102">Was-wäre-wenn-Szenario (Tabellenanalysetools für Excel)</span><span class="sxs-lookup"><span data-stu-id="627c3-102">What-If Scenario (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="627c3-103">![Schaltfläche für Was-wäre-wenn-Szenario in der Leiste "Tabellenanalysetools"](media/tat-whatif.gif "Schaltfläche für Was-wäre-wenn-Szenario in der Leiste "Tabellenanalysetools"")</span><span class="sxs-lookup"><span data-stu-id="627c3-103">![What If Scenario button in Table Analysis tools](media/tat-whatif.gif "What If Scenario button in Table Analysis tools")</span></span>

 <span data-ttu-id="627c3-104">Das **Was-wäre-wenn-** szenariotool analysiert Muster in vorhandenen Daten und ermöglicht es Ihnen, die Auswirkung zu bewerten, die Änderungen in einer Spalte auf den Wert einer anderen Spalte haben.</span><span class="sxs-lookup"><span data-stu-id="627c3-104">The **What-If** scenario tool analyzes patterns in existing data, and then enables you to evaluate the effect that changes in one column would have on the value of a different column.</span></span>

 <span data-ttu-id="627c3-105">Beispielsweise können Sie die Auswirkung einer Preiserhöhung für einen Artikel auf dessen Gesamtumsatz prüfen.</span><span class="sxs-lookup"><span data-stu-id="627c3-105">For example, you could explore the effect of raising the price of an item on its total sales.</span></span>

 <span data-ttu-id="627c3-106">Das Tool lässt beliebig viele Vorhersagen zu.</span><span class="sxs-lookup"><span data-stu-id="627c3-106">The tool is flexible about the number of predictions you can create.</span></span> <span data-ttu-id="627c3-107">Nachdem die erste Analyse abgeschlossen wurde, können Sie Änderungen für alle Daten in der Tabelle vorhersagen oder Testwerte nacheinander eingeben.</span><span class="sxs-lookup"><span data-stu-id="627c3-107">After the initial analysis is complete, you can either predict changes for all the data in the table, or enter test values one at a time.</span></span>

## <a name="using-the-what-if-scenario-tool"></a><span data-ttu-id="627c3-108">Verwenden des Tools für das Was-wäre-wenn-Szenario</span><span class="sxs-lookup"><span data-stu-id="627c3-108">Using the What-If Scenario Tool</span></span>

1.  <span data-ttu-id="627c3-109">Öffnen Sie eine Excel-Datentabelle.</span><span class="sxs-lookup"><span data-stu-id="627c3-109">Open an Excel data table.</span></span>

2.  <span data-ttu-id="627c3-110">Klicken Sie auf **Szenarios**und dann auf **Was-wäre-wenn**.</span><span class="sxs-lookup"><span data-stu-id="627c3-110">Click **Scenarios**, and then select **What-If**.</span></span>

3.  <span data-ttu-id="627c3-111">Wählen Sie im Feld **Szenario** die Spalte aus, die den Wert enthält, den Sie ändern möchten, und geben Sie die Änderung entweder als einen bestimmten Wert oder als Prozentsatz der Änderung (entweder erweitert oder verkleinert) für die aktuellen Werte an.</span><span class="sxs-lookup"><span data-stu-id="627c3-111">In the **Scenario** box, select the column that contains the value you will change, and specify the change either as a specific value or as a percentage of change (either increased or decreased) on the current values.</span></span>

4.  <span data-ttu-id="627c3-112">Geben Sie im Feld **Was geschieht mit** die Spalte an, für die Sie den Effekt bewerten möchten.</span><span class="sxs-lookup"><span data-stu-id="627c3-112">In the **What happens to** box, specify the column for which you want to assess the effect.</span></span>

5.  <span data-ttu-id="627c3-113">Klicken Sie optional auf **Spalten auswählen, die für die Analyse verwendet werden** sollen, um Spalten auszuwählen, die bei der Vorhersage wahrscheinlich nützlich sind.</span><span class="sxs-lookup"><span data-stu-id="627c3-113">Optionally, click **Choose columns to be used for analysis** to select columns that are likely to be useful in making the prediction.</span></span> <span data-ttu-id="627c3-114">Sie können die Auswahl von Spalten aufheben, die beim Erkennen von Mustern wahrscheinlich wenig nützlich sein werden, z. B. Zeilen-IDs oder Namen.</span><span class="sxs-lookup"><span data-stu-id="627c3-114">You can also deselect columns that are likely to be of little use in detecting patterns, such as row IDs or names.</span></span>

6.  <span data-ttu-id="627c3-115">Wählen Sie im Feld **Zeile oder Tabelle angeben** aus, ob die Auswirkung nur für die aktuell ausgewählte Zeile oder für den gesamten Satz von Daten in der Tabelle ausgewertet werden soll.</span><span class="sxs-lookup"><span data-stu-id="627c3-115">In the **Specify row or table** box, choose whether you want the impact assessed for the currently selected row only, or for the complete set of data in the table.</span></span>

7.  <span data-ttu-id="627c3-116">Wenn Sie in **dieser Zeile**auswählen, zeigt das Tool das Ergebnis im Dialogfeld an.</span><span class="sxs-lookup"><span data-stu-id="627c3-116">If you select **On this row**, the tool displays the result in the dialog box.</span></span> <span data-ttu-id="627c3-117">Sie können Ihre Auswahl ändern, um andere Szenarien zu testen, während das Dialogfeld geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="627c3-117">While the dialog box remains open, you can modify your selections to test other scenarios.</span></span>

8.  <span data-ttu-id="627c3-118">Wenn Sie die **gesamte Tabelle**auswählen, zeigt das Tool eine Statusmeldung im Dialogfeld an und fügt der ursprünglichen Datentabelle zwei neue Spalten hinzu.</span><span class="sxs-lookup"><span data-stu-id="627c3-118">If you select **Entire table**, the tool displays a status message in the dialog box, and adds two new columns to the original data table.</span></span> <span data-ttu-id="627c3-119">Klicken Sie auf **Schließen** , um die gesamten Ergebnisse im Arbeitsblatt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="627c3-119">Click **Close** to view the complete results in the worksheet.</span></span>

### <a name="requirements"></a><span data-ttu-id="627c3-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="627c3-120">Requirements</span></span>
 <span data-ttu-id="627c3-121">Für dieses Tool wird der Microsoft Logistic Regression-Algorithmus verwendet, der Vorhersagen für numerische oder diskrete Werte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="627c3-121">This tool uses the Microsoft Logistic Regression algorithm, which supports prediction of either numeric or discrete values.</span></span> <span data-ttu-id="627c3-122">Um aber die besten Ergebnisse zu erzielen, sollten Sie die folgenden bewährten Methoden anwenden:</span><span class="sxs-lookup"><span data-stu-id="627c3-122">However, to achieve the best results, we suggest the following best practices:</span></span>

-   <span data-ttu-id="627c3-123">Wählen Sie Spalten für die Analyse aus, die nützliche Informationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="627c3-123">Select columns for analysis that contain useful information.</span></span>

-   <span data-ttu-id="627c3-124">Wenn Sie zu wenige Spalten einschließen, kann das Erzielen von Ergebnissen erschwert werden.</span><span class="sxs-lookup"><span data-stu-id="627c3-124">If you include too few columns it may be difficult to obtain a result.</span></span>

-   <span data-ttu-id="627c3-125">Wenn Sie die Option **mit Wert** verwenden, müssen Sie einen Wert in das Feld eingeben oder einen Wert aus der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="627c3-125">If you use the **To value** option, you must type a value in the box or select a value from the list.</span></span>

-   <span data-ttu-id="627c3-126">Wenn Sie die Option **Prozentsatz** verwenden, legen Sie die Änderung als prozentuale Erhöhung oder Verringerung fest.</span><span class="sxs-lookup"><span data-stu-id="627c3-126">If you use the **Percentage** option, set the change as a percentage increase or decrease.</span></span> <span data-ttu-id="627c3-127">Der Standardwert ist 120 Prozent, das bedeutet eine Erhöhung von 20 Prozent über den aktuellen Wert.</span><span class="sxs-lookup"><span data-stu-id="627c3-127">The default is 120%, meaning a 20% increase over the current value.</span></span>

> [!NOTE]
>  <span data-ttu-id="627c3-128">Wenn Sie keinen Wert festlegen, wird möglicherweise ein Fehler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="627c3-128">If you do not set a value, you might receive an error.</span></span>

## <a name="understanding-the-results-of-what-if-analysis"></a><span data-ttu-id="627c3-129">Grundlegendes zu den Ergebnissen der Was-wäre-wenn-Analyse</span><span class="sxs-lookup"><span data-stu-id="627c3-129">Understanding the Results of What-If Analysis</span></span>
 <span data-ttu-id="627c3-130">Wenn Sie ein **Was-wäre-wenn-** Szenario erstellen, erledigt das Tool drei Dinge:</span><span class="sxs-lookup"><span data-stu-id="627c3-130">When you create a **What-If** scenario, the tool does three things:</span></span>

-   <span data-ttu-id="627c3-131">Es wird eine Data Mining-Struktur erstellt, in der wichtige Fakten zu den Daten in der Tabelle gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="627c3-131">Creates a data mining structure that stores key facts about the data in your table.</span></span>

-   <span data-ttu-id="627c3-132">Es wird anhand der Daten ein Logistic Regression-Miningmodell erstellt.</span><span class="sxs-lookup"><span data-stu-id="627c3-132">Creates a logistic regression mining model based on the data.</span></span>

-   <span data-ttu-id="627c3-133">Es wird eine Vorhersageabfrage für alle von Ihnen angegebenen Werte erstellt.</span><span class="sxs-lookup"><span data-stu-id="627c3-133">Creates a prediction query for each of the values you specify.</span></span>

 <span data-ttu-id="627c3-134">Sie können alle Vorhersagen gleichzeitig ausgeben, indem Sie die **gesamte Tabelle**angeben.</span><span class="sxs-lookup"><span data-stu-id="627c3-134">You can output all the predictions at one time by specifying **Entire table**.</span></span> <span data-ttu-id="627c3-135">Vom Tool werden daraufhin in der ursprünglichen Datentabelle zwei neue Spalten erstellt.</span><span class="sxs-lookup"><span data-stu-id="627c3-135">The tool then creates two new columns in the original data table.</span></span>

 <span data-ttu-id="627c3-136">Die der Tabelle hinzugefügten Spalten enthalten zwei Informationstypen: den geänderten vorhergesagten Wert sowie das Vertrauen in den Wert.</span><span class="sxs-lookup"><span data-stu-id="627c3-136">The columns that are added to the table contain two types of information: the predicted value given the change, and its confidence.</span></span> <span data-ttu-id="627c3-137">Mit Vertrauen ist die Wahrscheinlichkeit gemeint, dass die Vorhersage zutrifft.</span><span class="sxs-lookup"><span data-stu-id="627c3-137">Confidence means the probability that the prediction is correct.</span></span>

 <span data-ttu-id="627c3-138">Sie können Änderungswerte auch nacheinander im Dialogfeld eingeben und die Vorhersagen anschließend interaktiv anzeigen.</span><span class="sxs-lookup"><span data-stu-id="627c3-138">You can also enter change values one by one in the dialog box, and view the predictions interactively.</span></span> <span data-ttu-id="627c3-139">Dies entspricht dem Erstellen einer *SINGLETON-Vorhersage Abfrage*.</span><span class="sxs-lookup"><span data-stu-id="627c3-139">This is the same as creating a *singleton prediction query*.</span></span> <span data-ttu-id="627c3-140">Die Ergebnisse der Vorhersageabfrage werden zusammen mit den folgenden Informationen ausgegeben: dem Erfolg oder Fehler der Vorhersage, dem vorhergesagten Wert sowie dem Vertrauensgrad.</span><span class="sxs-lookup"><span data-stu-id="627c3-140">The results of the prediction query are output with the following information: the success or failure of prediction, the predicted value, and the confidence level.</span></span> <span data-ttu-id="627c3-141">Der Vertrauensgrad wird als Leiste mit einer gepunkteten Linie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="627c3-141">The confidence level is shown as a bar that contains a dotted line.</span></span> <span data-ttu-id="627c3-142">Je länger die gepunktete Linie ist, desto höher ist das Vertrauen in das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="627c3-142">The longer the dotted line, the higher the confidence in the result.</span></span>

 <span data-ttu-id="627c3-143">Wenn Sie z. b. versuchen, die Auswirkung der Erhöhung des Alters des Kunden auf den Kauf zu ermitteln und das Alter des Kunden auf 25 zu erhöhen, fragt das **Was-wäre-wenn-** Tool das Data Mining Modell ab und gibt das folgende Ergebnis zurück:</span><span class="sxs-lookup"><span data-stu-id="627c3-143">For example, if you are trying to determine the effect of increasing the customer's age on the customer's willingness to buy, and increase the customer's age to 25, the **What-If** tool queries the data mining model and returns the following result:</span></span>

 <span data-ttu-id="627c3-144">**Bei der Was-wäre-wenn-Analyse für Fahrradverkäufe wurde eine Lösung gefunden.**</span><span class="sxs-lookup"><span data-stu-id="627c3-144">**What-If Analysis for Purchases Bicycle has found a solution.**</span></span>

 <span data-ttu-id="627c3-145">**'Fahrradverkäufe' = ja**</span><span class="sxs-lookup"><span data-stu-id="627c3-145">**'Purchases Bicycle' = yes**</span></span>

 <span data-ttu-id="627c3-146">**Vertrauen: Durchschnittlich**</span><span class="sxs-lookup"><span data-stu-id="627c3-146">**Confidence: Fair**</span></span>

 <span data-ttu-id="627c3-147">Da dieses Ergebnis auf einer vorhandenen Zeile in der Datentabelle beruht, bedeutet das bei einem bestimmten Kunden Folgendes: Wenn alle anderen Werte zum Kunden unverändert bleiben, das Alter des Kunden jedoch auf 25 erhöht wird, kauft der Kunde wahrscheinlich ein Fahrrad.</span><span class="sxs-lookup"><span data-stu-id="627c3-147">Because this result is based on an existing row in the data table, it means that, for a particular customer, if all else about the customer stayed the same but the customer's age was increased to 25, the customer would likely buy a bicycle.</span></span>

 <span data-ttu-id="627c3-148">Die Ausgabe der Vorhersagen in die ursprüngliche Datentabelle vereinfacht möglicherweise die Überprüfung, ob die Vorhersagen nützlich sind.</span><span class="sxs-lookup"><span data-stu-id="627c3-148">Outputting the predictions to the original data table might make it easier to determine whether the predictions are useful.</span></span>

## <a name="related-tools"></a><span data-ttu-id="627c3-149">Verwandte Tools</span><span class="sxs-lookup"><span data-stu-id="627c3-149">Related Tools</span></span>
 <span data-ttu-id="627c3-150">Der Data Mining-Client für Excel, bei dem es sich um ein separates Add-In mit erweiterter Data Mining-Funktionalität handelt, enthält Assistenten zum Erstellen von Data Mining-Modellen, die Verhalten vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="627c3-150">The Data Mining Client for Excel, which is a separate add-in that provides more advanced data mining functionality, includes wizards for creating data mining models that predict behavior.</span></span> <span data-ttu-id="627c3-151">Weitere Informationen finden Sie unter [Erstellen eines Data Mining-Modells](creating-a-data-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="627c3-151">For more information, see [Creating a Data Mining Model](creating-a-data-mining-model.md).</span></span>

 <span data-ttu-id="627c3-152">Weitere Informationen zum Algorithmus, der vom **Was-wäre-wenn-Szenario-** Tool verwendet wird, finden Sie im Thema "Microsoft Logistic Regression-Algorithmus" in SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="627c3-152">For more information about the algorithm used by the **What-If** scenario tool, see the topic "Microsoft Logistic Regression Algorithm" in SQL Server Books Online.</span></span>

## <a name="see-also"></a><span data-ttu-id="627c3-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="627c3-153">See Also</span></span>
 [<span data-ttu-id="627c3-154">Tabellenanalysetools für Excel</span><span class="sxs-lookup"><span data-stu-id="627c3-154">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)


