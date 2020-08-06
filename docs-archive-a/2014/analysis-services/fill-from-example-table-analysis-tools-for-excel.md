---
title: Aus Beispiel füllen (Tabellenanalyse Tools für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Table Analysis tools
- fill from example
ms.assetid: dac57d8f-1c65-4878-8ea0-9c680df5e4fb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 69ff9f554c51240eb6f9151718d30677bfb57996
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700479"
---
# <a name="fill-from-example-table-analysis-tools-for-excel"></a><span data-ttu-id="c2d8b-102">Aus Beispiel füllen (Tabellenanalysetools für Excel)</span><span class="sxs-lookup"><span data-stu-id="c2d8b-102">Fill From Example (Table Analysis Tools for Excel)</span></span>
  <span data-ttu-id="c2d8b-103">![Aus Beispiel füllen (Schaltfläche in Tabellenanalysetools)](media/tat-fillex.gif "Aus Beispiel füllen (Schaltfläche in Tabellenanalysetools)")</span><span class="sxs-lookup"><span data-stu-id="c2d8b-103">![Fill From Example button in Table Analysis Tools](media/tat-fillex.gif "Fill From Example button in Table Analysis Tools")</span></span>  
  
 <span data-ttu-id="c2d8b-104">Das Tool **aus Beispiel füllen** unterstützt Sie beim Erstellen neuer Datenspalten auf der Grundlage vorhandener Werte.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-104">The **Fill From Example** tool helps you build new columns of data based on existing values.</span></span>  
  
 <span data-ttu-id="c2d8b-105">Nehmen Sie beispielsweise an, dass Ihre Daten eine Spalte " **Purchase Amount** ", eine Spalte "Bestell **Menge** " und eine Spalte " **Premier Customer** " enthalten, die auf einer Formel basiert, die die anderen Spalten verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-105">For example, suppose your data contains a **Purchase Amount** column, an **Orders Quantity** column, and a **Premier Customer** column that is based on some formula using the other columns.</span></span> <span data-ttu-id="c2d8b-106">Wenn die Spalte **Premier Customer** viele leere Zeilen enthält, können Sie die Spalten **Purchase Amount** und **Order** Amount als Eingaben verwenden, um die fehlenden Werte abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-106">If the  **Premier Customer** column contains many blank rows, you could use the **Purchase Amount** and **Orders Quantity** columns as the inputs, to infer the missing values.</span></span> <span data-ttu-id="c2d8b-107">Das Tool analysiert die vorhandenen Datenmuster in Kombination mit den von Ihnen eingegebenen Beispielen und trifft eine Vorhersage dazu, welche Kategorie den einzelnen Kunden zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-107">The tool analyzes existing patterns in the data together with the examples you entered, and predicts which category to assign to each customer.</span></span>  
  
 <span data-ttu-id="c2d8b-108">Wenn Sie mit den Ergebnissen nicht zufrieden sind, können Sie sie optimieren, indem Sie weitere Beispiele bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-108">If you are not satisfied with the results, you can refine the results by providing more examples.</span></span>  
  
## <a name="using-the-fill-from-example-tool"></a><span data-ttu-id="c2d8b-109">Verwenden des Tools 'Aus Beispiel füllen'</span><span class="sxs-lookup"><span data-stu-id="c2d8b-109">Using the Fill From Example Tool</span></span>  
  
1.  <span data-ttu-id="c2d8b-110">Klicken Sie im Menüband **analysieren** auf **aus Beispiel füllen**.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-110">In the **Analyze** ribbon, click **Fill From Example**.</span></span>  
  
2.  <span data-ttu-id="c2d8b-111">Basierend auf der Analyse der Daten wird die auszufüllende Spalte automatisch vom Tool ausgefüllt. Diese Empfehlung können Sie dann übernehmen oder überschreiben.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-111">The tool will automatically pick a column to fill based on analysis of the data, and you can either accept or override this suggestion.</span></span>  
  
3.  <span data-ttu-id="c2d8b-112">Erstellen Sie eine Spalte für die neuen Daten, und geben Sie Beispiele für die Daten ein, für die Sie eine Vorhersage treffen möchten.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-112">Create a column for the new data, and type in examples of the data that you want to predict.</span></span> <span data-ttu-id="c2d8b-113">Stellen Sie sicher, dass für jeden vorherzusagenden Wert mindestens ein Beispiel vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-113">Make sure that there is at least one example for every value that you want to predict.</span></span> <span data-ttu-id="c2d8b-114">Wenn Daten in eine bereits vorhandene Spalte eingetragen werden sollen, wählen Sie die Spalte mit den fehlenden Werten aus.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-114">If you are filling in data in an existing column, select the column that has missing values.</span></span>  
  
4.  <span data-ttu-id="c2d8b-115">Klicken Sie optional auf **Spalten auswählen, die in der Analyse verwendet werden sollen**.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-115">Optionally, click **Choose columns to be used in analysis**.</span></span> <span data-ttu-id="c2d8b-116">Geben Sie im Dialogfeld **Erweiterte Spaltenauswahl** die Spalten an, die am wahrscheinlichsten beim Ausfüllen der fehlenden Daten nützlich sein werden.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-116">In the **Advanced Columns Selection** dialog box, specify the columns that are most likely to be useful when filling in the missing data.</span></span>  
  
     <span data-ttu-id="c2d8b-117">Sie wissen beispielsweise aus Erfahrung, dass zwischen einer bestimmten Spalte und der Spalte mit den fehlenden Werten ein kausaler Zusammenhang besteht. In diesem Fall können Sie die Auswahl anderer Spalten aufheben, um bessere Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-117">For example, if you know from experience that there is a causal effect between one column and the column that has missing values, you can deselect other columns to get better results.</span></span>  
  
     <span data-ttu-id="c2d8b-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="c2d8b-119">Klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-119">Click **Run**.</span></span>  
  
     <span data-ttu-id="c2d8b-120">Wenn die Analyse fertiggestellt ist, erstellt das Tool ein neues **Muster** Arbeitsblatt, das die Ergebnisse der Analyse enthält.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-120">When analysis is complete, the tool creates a new **Patterns** worksheet that contains the results of analysis.</span></span> <span data-ttu-id="c2d8b-121">Der Bericht zeigt an, welche Regeln oder wichtigen Einflussfaktoren gefunden wurden und wie hoch die Wahrscheinlichkeit für die einzelnen Regeln ist.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-121">The report lists the rules, or key influencers, that were found, and shows the probability for each rule.</span></span>  
  
     <span data-ttu-id="c2d8b-122">Durch das Tool wird der ursprünglichen Datentabelle außerdem automatisch eine Spalte hinzugefügt, die die neuen Werte enthält.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-122">The tool also automatically adds a column that contains the new values to the original data table.</span></span> <span data-ttu-id="c2d8b-123">Sie können diese Werte überprüfen und mit den ursprünglichen Werten vergleichen.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-123">You can review the values and compare them against the original.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="c2d8b-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c2d8b-124">Requirements</span></span>  
 <span data-ttu-id="c2d8b-125">Sie können nur Daten verwenden, die sich in Spalten befinden.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-125">You can only work with data in columns.</span></span> <span data-ttu-id="c2d8b-126">Verwenden Sie die Einfügen/Transponieren-Funktion in Excel, um aufzufüllende Datenreihen, die in einer Zeile gespeichert sind, in das Spaltenformat umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-126">If the series that you want to fill is stored in a row, you can use the Paste, Transpose function in Excel to change the data to a columnar format.</span></span>  
  
## <a name="understanding-the-pattern-report"></a><span data-ttu-id="c2d8b-127">Grundlegendes zum Musterbericht</span><span class="sxs-lookup"><span data-stu-id="c2d8b-127">Understanding the Pattern Report</span></span>  
 <span data-ttu-id="c2d8b-128">Wenn Sie das Tool " **aus Beispiel füllen** " ausführen, wird ein Bericht erstellt, der weitere Informationen zu den erkannten Mustern bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-128">When you run the **Fill From Example** tool, a report is created that provides more information about the patterns that were detected.</span></span> <span data-ttu-id="c2d8b-129">Diese Muster werden zum Extrapolieren der neuen Datenwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-129">These patterns are used for extrapolating new data values.</span></span>  
  
 <span data-ttu-id="c2d8b-130">Im Musterbericht werden die wichtigen Einflussfaktoren für jeden vorhergesagten Wert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-130">The Pattern Report shows the key influencers for each value that was predicted.</span></span> <span data-ttu-id="c2d8b-131">Jeder Einflussfaktor bzw. jede Regel wird als eine Kombination aus einer Spalte, des Werts in dieser Spalte und der relativen Auswirkung der Regel auf die Vorhersage beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-131">Each influencer or rule is described as a combination of a column, the value in that column, and the relative impact of the rule on the prediction.</span></span>  
  
 <span data-ttu-id="c2d8b-132">Wenn Sie beispielsweise ein Arbeitsblatt mit den Entfernungen zu Lieferadressen für Bestellungen ausfüllen möchten, dann nehmen Sie logischerweise an, dass die Lieferadresse einen großen Einfluss auf die Entfernung hat.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-132">For example, if you were trying to fill in a worksheet that shows the shipping distance for orders, you might logically expect the destination to have a strong impact on the value for shipping distance.</span></span> <span data-ttu-id="c2d8b-133">In diesem Fall enthält der Bericht möglicherweise folgende Zeile:</span><span class="sxs-lookup"><span data-stu-id="c2d8b-133">In this case, the report might contain the following row:</span></span>  
  
|<span data-ttu-id="c2d8b-134">Spalte</span><span class="sxs-lookup"><span data-stu-id="c2d8b-134">Column</span></span>|<span data-ttu-id="c2d8b-135">Wert</span><span class="sxs-lookup"><span data-stu-id="c2d8b-135">Value</span></span>|<span data-ttu-id="c2d8b-136">Begünstigt</span><span class="sxs-lookup"><span data-stu-id="c2d8b-136">Favors</span></span>|<span data-ttu-id="c2d8b-137">Relative Auswirkung</span><span class="sxs-lookup"><span data-stu-id="c2d8b-137">Relative Impact</span></span>|  
|------------|-----------|------------|---------------------|  
|<span data-ttu-id="c2d8b-138">Bundesland/Kanton/PLZ</span><span class="sxs-lookup"><span data-stu-id="c2d8b-138">StateProvinceCode</span></span>|<span data-ttu-id="c2d8b-139">AB</span><span class="sxs-lookup"><span data-stu-id="c2d8b-139">AB</span></span>|<span data-ttu-id="c2d8b-140">>500-Kilometer</span><span class="sxs-lookup"><span data-stu-id="c2d8b-140">>500 kilometers</span></span>|<span data-ttu-id="c2d8b-141">80 %</span><span class="sxs-lookup"><span data-stu-id="c2d8b-141">80%</span></span>|  
  
 <span data-ttu-id="c2d8b-142">Dies bedeutet, dass der Wert ab in der Spalte **StateProvinceCode** stark eine Versand Entfernung von >500 Kilometer vorhersagt.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-142">This means that the value AB in the **StateProvinceCode** column strongly predicts a shipping distance of >500 kilometers.</span></span>  
  
 <span data-ttu-id="c2d8b-143">In der Regel beruhen die Vorhersagen auf weit komplexeren Mustern als in diesem Beispiel, und der Bericht enthält möglicherweise zahlreiche Regelzeilen für jede Vorhersage.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-143">Typically, predictions are based on patterns that are far more complex than this example, and the report may contain many rows of rules for each prediction.</span></span> <span data-ttu-id="c2d8b-144">Die Auswirkungen der einzelnen Regeln werden kombiniert, um den vorhergesagten Wert abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-144">The effect of all the rules are combined to derive the predicted value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c2d8b-145">Die **relative Auswirkung** wird als schattierter Balken angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-145">**Relative Impact** is shown as a shaded bar.</span></span> <span data-ttu-id="c2d8b-146">Je länger der Balken, desto größer ist die Wahrscheinlichkeit, dass die Regel für den ausgefüllten Wert zutrifft.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-146">The longer the bar, the greater the probability that this rule is predictive of the filled-in value.</span></span>  
  
 <span data-ttu-id="c2d8b-147">Das Tool fügt der ursprünglichen Datentabelle mit dem Namen erweitert auch eine neue Spalte hinzu \<column name> .</span><span class="sxs-lookup"><span data-stu-id="c2d8b-147">The tool also adds a new column to the original data table, named \<column name> Extended.</span></span>  
  
 <span data-ttu-id="c2d8b-148">Wenn die ursprüngliche Datenspalte einen Wert enthält, wird dieser Wert in die neue Spalte kopiert.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-148">If the original data column contained a value, that value is copied into the new column.</span></span> <span data-ttu-id="c2d8b-149">Wenn die ursprüngliche Spalte jedoch eine leere Zelle enthält, enthält die neue Spalte den durch den Assistenten vorhergesagten Wert.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-149">However, if the original column contained a blank cell, the new column contains the value that was predicted by the wizard.</span></span>  
  
## <a name="related-tools-and-information"></a><span data-ttu-id="c2d8b-150">Verwandte Tools und Informationen</span><span class="sxs-lookup"><span data-stu-id="c2d8b-150">Related Tools and Information</span></span>  
 <span data-ttu-id="c2d8b-151">Sie können auch den Assistenten zum durch [Suchen von Daten](explore-data-sql-server-data-mining-add-ins.md) verwenden, der im Data Mining-Client für Excel verfügbar ist, um die Verteilung von Werten in einer Excel-Spalte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c2d8b-151">You can also use the [Explore Data](explore-data-sql-server-data-mining-add-ins.md) wizard, available in the Data Mining Client for Excel, to examine the distribution of values in an Excel column.</span></span> <span data-ttu-id="c2d8b-152">Weitere Informationen finden Sie unter durch [Suchen und Bereinigen von Daten](exploring-and-cleaning-data.md).</span><span class="sxs-lookup"><span data-stu-id="c2d8b-152">For more information, see [Exploring and Cleaning Data](exploring-and-cleaning-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2d8b-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c2d8b-153">See Also</span></span>  
 [<span data-ttu-id="c2d8b-154">Tabellenanalysetools für Excel</span><span class="sxs-lookup"><span data-stu-id="c2d8b-154">Table Analysis Tools for Excel</span></span>](table-analysis-tools-for-excel.md)  
  
  
