---
title: Erstellen von Zeitreihen Vorhersagen (Data Mining-Tutorial für Fortgeschrittene) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: fb22cffa-ac99-4d34-ac4a-9c93068e33e8
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a1175cdffd1512e0cb876b9565dd0727a9f094c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615243"
---
# <a name="creating-time-series-predictions-intermediate-data-mining-tutorial"></a><span data-ttu-id="49485-102">Erstellen von Zeitreihenvorhersagen (Data Mining-Lernprogramm für Fortgeschrittene)</span><span class="sxs-lookup"><span data-stu-id="49485-102">Creating Time Series Predictions (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="49485-103">In den vorherigen Aufgaben dieser Lektion haben Sie ein Zeitreihenmodell erstellt und die Ergebnisse untersucht.</span><span class="sxs-lookup"><span data-stu-id="49485-103">In the previous tasks in this lesson, you created a time series model and explored the results.</span></span> <span data-ttu-id="49485-104">[!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] erstellt standardmäßig immer einen Satz von fünf (5) Vorhersagen für ein Zeitreihenmodell und zeigt die vorhergesagten Werte in einem Prognosediagramm an.</span><span class="sxs-lookup"><span data-stu-id="49485-104">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] always creates a set of five (5) predictions for a time series model and displays the predicted values as part of the forecasting chart.</span></span> <span data-ttu-id="49485-105">Sie können Prognosen jedoch auch mithilfe von Data Mining Extensions (DMX)-Vorhersageabfragen erzeugen.</span><span class="sxs-lookup"><span data-stu-id="49485-105">However, you can also create forecasts by building Data Mining Extensions (DMX) prediction queries.</span></span>  
  
 <span data-ttu-id="49485-106">In dieser Aufgabe erstellen Sie eine Vorhersageabfrage, mit der die gleichen Vorhersagen wie im Viewer generiert werden.</span><span class="sxs-lookup"><span data-stu-id="49485-106">In this task, you will create a prediction query that generates the same predictions that you saw in the viewer.</span></span> <span data-ttu-id="49485-107">Diese Aufgabe geht davon aus, dass Sie die Lektionen im Lernprogramm zu den Data Mining-Grundlagen bereits abgeschlossen haben und dass Sie mit der Verwendung des Generators für Vorhersageabfragen vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="49485-107">This task assumes that you have already completed the lessons in the Basic Data Mining Tutorial and are familiar with how to use Prediction Query Builder.</span></span> <span data-ttu-id="49485-108">Im Folgenden lernen Sie, wie Sie Abfragen für Zeitreihenmodelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="49485-108">You will now learn how to create queries specific to time series models.</span></span>  
  
## <a name="creating-time-series-predictions"></a><span data-ttu-id="49485-109">Erstellen von Zeitreihenvorhersagen</span><span class="sxs-lookup"><span data-stu-id="49485-109">Creating Time Series Predictions</span></span>  
 <span data-ttu-id="49485-110">Der erste Schritt beim Erstellen einer Vorhersageabfrage besteht normalerweise in der Auswahl eines Miningmodells und einer Eingabetabelle.</span><span class="sxs-lookup"><span data-stu-id="49485-110">Typically, the first step in creating a prediction query is to select a mining model and input table.</span></span> <span data-ttu-id="49485-111">Ein Zeitreihenmodell benötigt jedoch für reguläre Vorhersagen keine zusätzliche Eingabe.</span><span class="sxs-lookup"><span data-stu-id="49485-111">However, a time series model does not require additional input for a regular prediction.</span></span> <span data-ttu-id="49485-112">Es ist daher nicht erforderlich, eine neue Datenquelle für Vorhersagen anzugeben, wenn Sie dem Modell keine Daten hinzufügen oder Daten ersetzen.</span><span class="sxs-lookup"><span data-stu-id="49485-112">Therefore, you do not need to specify a new source of data when making predictions, unless you are adding data to the model or replacing the data.</span></span>  
  
 <span data-ttu-id="49485-113">Sie müssen für diese Lektion die Anzahl der Vorhersageschritte angeben.</span><span class="sxs-lookup"><span data-stu-id="49485-113">For this lesson, you must specify the number of prediction steps.</span></span> <span data-ttu-id="49485-114">Sie können den Namen der Reihe angeben, um eine Vorhersage für eine bestimmte Kombination aus Produkt und Region zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="49485-114">You can specify the series name, to get a prediction for a particular combination of a product and a region.</span></span>  
  
#### <a name="to-select-a-model-and-input-table"></a><span data-ttu-id="49485-115">So wählen Sie ein Modell und eine Eingabetabelle aus</span><span class="sxs-lookup"><span data-stu-id="49485-115">To select a model and input table</span></span>  
  
1.  <span data-ttu-id="49485-116">Klicken Sie im Data Mining-Designer auf der Registerkarte **Mining Modellvorhersage** im Feld **Mining Modell** auf **Modell auswählen**.</span><span class="sxs-lookup"><span data-stu-id="49485-116">On the **Mining Model Prediction** tab of the Data Mining Designer, in the **Mining Model** box, click **Select Model**.</span></span>  
  
2.  <span data-ttu-id="49485-117">Erweitern Sie im Dialogfeld **Mining Modell auswählen** die Planungsstruktur, wählen Sie das **Vorhersage** Modell aus der Liste aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="49485-117">In the **Select Mining Model** dialog box, expand the Forecasting structure, select the **Forecasting** model from the list, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="49485-118">Ignorieren Sie das Kontrollkästchen **Eingabe Tabelle (n) auswählen** .</span><span class="sxs-lookup"><span data-stu-id="49485-118">Ignore the **Select Input Table(s)** box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="49485-119">Bei einem Zeitreihenmodell müssen Sie keine separaten Eingabewerte angeben, wenn Sie keine Kreuzvorhersagen treffen.</span><span class="sxs-lookup"><span data-stu-id="49485-119">For a time series model, you do not need to specify a separate input unless you are doing cross-prediction.</span></span>  
  
4.  <span data-ttu-id="49485-120">Klicken Sie in der Spalte **Quelle** im Raster auf der Registerkarte **Mining Modellvorhersage** auf die Zelle in der ersten leeren Zeile, und wählen Sie dann **Mining Modell prognostizieren**aus.</span><span class="sxs-lookup"><span data-stu-id="49485-120">In the **Source** column, in the grid on the **Mining Model Prediction** tab, click the cell in the first empty row, and then select **Forecasting mining model**.</span></span>  
  
5.  <span data-ttu-id="49485-121">Wählen Sie in der Spalte **Feld** die Option **Modellbereich**aus.</span><span class="sxs-lookup"><span data-stu-id="49485-121">In the **Field** column, select **Model Region**.</span></span>  
  
     <span data-ttu-id="49485-122">Auf diese Weise wird der Bezeichner für die Reihe zur Vorhersageabfrage hinzugefügt, um anzugeben, auf welche Kombination aus Modell und Region sich die Vorhersage bezieht.</span><span class="sxs-lookup"><span data-stu-id="49485-122">This action adds the series identifier to the prediction query to indicate the combination of model and region to which the prediction applies.</span></span>  
  
6.  <span data-ttu-id="49485-123">Klicken Sie in der Spalte **Quelle** auf die nächste leere Zeile, und wählen Sie dann **Vorhersagefunktion**aus.</span><span class="sxs-lookup"><span data-stu-id="49485-123">Click the next empty row in the **Source** column, and then select **Prediction Function**.</span></span>  
  
7.  <span data-ttu-id="49485-124">Wählen Sie in der Spalte **Feld** die Option **prättimeseries**aus.</span><span class="sxs-lookup"><span data-stu-id="49485-124">In the **Field** column, select **PredictTimeSeries**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="49485-125">Sie können auch die `Predict`-Funktion mit Zeitreihenmodellen verwenden.</span><span class="sxs-lookup"><span data-stu-id="49485-125">You can also use the `Predict` function with time series models.</span></span> <span data-ttu-id="49485-126">Standardmäßig wird durch die Vorhersagefunktion jedoch nur eine Vorhersage für jede Reihe erstellt.</span><span class="sxs-lookup"><span data-stu-id="49485-126">However, by default, the Predict function creates only one prediction for each series.</span></span> <span data-ttu-id="49485-127">Wenn Sie also mehrere Vorhersage Schritte angeben möchten, müssen Sie die Funktion " **prättimeseries** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="49485-127">Therefore, to specify multiple prediction steps, you must use the **PredictTimeSeries** function.</span></span>  
  
8.  <span data-ttu-id="49485-128">Wählen Sie im Bereich **Mining Modell** die Mining Modell Spalte Amount aus **.**</span><span class="sxs-lookup"><span data-stu-id="49485-128">In the **Mining Model** pane, select the mining model column, **Amount.**</span></span> <span data-ttu-id="49485-129">Ziehen Sie Amount in das Feld **Kriterium/Argument** für die Funktion " **prättimeseries** ", die Sie zuvor hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="49485-129">Drag Amount to the **Criteria/Arguments** box for the **PredictTimeSeries** function that you added earlier.</span></span>  
  
9. <span data-ttu-id="49485-130">Klicken Sie auf das Feld **Kriterium/Argument** , und geben Sie nach dem Feldnamen ein Komma und anschließend **5**ein.</span><span class="sxs-lookup"><span data-stu-id="49485-130">Click the **Criteria/Arguments** box, and type a comma, followed by **5**, after the field name.</span></span>  
  
     <span data-ttu-id="49485-131">Der Text im Feld **Kriterium/Argument** sollte nun Folgendes anzeigen:</span><span class="sxs-lookup"><span data-stu-id="49485-131">The text in the **Criteria/Arguments** box should now display the following:</span></span>  
  
     `[Forecasting].[Amount],5`  
  
10. <span data-ttu-id="49485-132">Geben Sie in der Spalte **Alias** den Namen ein `PredictAmount` .</span><span class="sxs-lookup"><span data-stu-id="49485-132">In the **Alias** column, type `PredictAmount`.</span></span>  
  
11. <span data-ttu-id="49485-133">Klicken Sie in der Spalte **Quelle** auf die nächste leere Zeile, und wählen Sie dann erneut **Vorhersagefunktion** aus.</span><span class="sxs-lookup"><span data-stu-id="49485-133">Click the next empty row in the **Source** column, and then select **Prediction Function** again.</span></span>  
  
12. <span data-ttu-id="49485-134">Wählen Sie in der Spalte **Feld** die Option **prättimeseries**aus.</span><span class="sxs-lookup"><span data-stu-id="49485-134">In the **Field** column, select **PredictTimeSeries**.</span></span>  
  
13. <span data-ttu-id="49485-135">Wählen Sie im Bereich **Mining Modell** die Spalten Menge aus, und ziehen Sie Sie dann in das Feld **Kriterium/Argument** für die zweite Funktion von " **vorherentimeseries** ".</span><span class="sxs-lookup"><span data-stu-id="49485-135">In the **Mining Model** pane, select the column Quantity, and then drag it into the **Criteria/Arguments** box for the second **PredictTimeSeries** function.</span></span>  
  
14. <span data-ttu-id="49485-136">Klicken Sie auf das Feld **Kriterium/Argument** , und geben Sie nach dem Feldnamen ein Komma und anschließend **5**ein.</span><span class="sxs-lookup"><span data-stu-id="49485-136">Click the **Criteria/Arguments** box, and type a comma, followed by **5**, after the field name.</span></span>  
  
     <span data-ttu-id="49485-137">Der Text im Feld **Kriterium/Argument** sollte nun Folgendes anzeigen:</span><span class="sxs-lookup"><span data-stu-id="49485-137">The text in the **Criteria/Arguments** box should now display the following:</span></span>  
  
     `[Forecasting].[ Quantity],5`  
  
15. <span data-ttu-id="49485-138">Geben Sie in der Spalte **Alias** den Namen ein `PredictQuantity` .</span><span class="sxs-lookup"><span data-stu-id="49485-138">In the **Alias** column, type `PredictQuantity`.</span></span>  
  
16. <span data-ttu-id="49485-139">Klicken Sie **auf zur Abfrageergebnis Sicht wechseln**.</span><span class="sxs-lookup"><span data-stu-id="49485-139">Click **Switch to query result view**.</span></span>  
  
     <span data-ttu-id="49485-140">Die Abfrageergebnisse werden im Tabellenformat angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49485-140">The results of the query are displayed in tabular format.</span></span>  
  
 <span data-ttu-id="49485-141">Im Generator für Vorhersageabfragen haben Sie drei verschiedene Ergebnistypen erstellt, einen für Werte aus einer Spalte und zwei zum Abrufen von Werten aus einer Vorhersagefunktion.</span><span class="sxs-lookup"><span data-stu-id="49485-141">Remember that you created three different types of results in the query builder, one that uses values from a column, and two that get predicted values from a prediction function.</span></span> <span data-ttu-id="49485-142">Aus diesem Grund enthalten die Ergebnisse der Abfrage drei separate Spalten.</span><span class="sxs-lookup"><span data-stu-id="49485-142">Therefore, the results of the query contain three separate columns.</span></span> <span data-ttu-id="49485-143">Die erste Spalte enthält die Liste der Kombinationen aus Produkt und Region.</span><span class="sxs-lookup"><span data-stu-id="49485-143">The first column contains the list of product and region combinations.</span></span> <span data-ttu-id="49485-144">Die zweite und dritte Spalte enthalten jeweils eine geschachtelte Tabelle mit Vorhersageergebnissen.</span><span class="sxs-lookup"><span data-stu-id="49485-144">The second and third columns each contain a nested table of prediction results.</span></span> <span data-ttu-id="49485-145">Jede geschachtelte Tabelle enthält die Zeitschritte und vorhergesagten Werte, wie in der nachfolgenden Tabelle dargestellt:</span><span class="sxs-lookup"><span data-stu-id="49485-145">Each nested table contains the time step and predicted values, such as the following table:</span></span>  
  
 <span data-ttu-id="49485-146">Beispielergebnisse (Mengen werden auf zwei Dezimalstellen gerundet):</span><span class="sxs-lookup"><span data-stu-id="49485-146">Example results (amounts are truncated to two decimal places):</span></span>  
  
 <span data-ttu-id="49485-147">**M200 Europe-prätbetrag**</span><span class="sxs-lookup"><span data-stu-id="49485-147">**M200 Europe PredictAmount**</span></span>  
  
|<span data-ttu-id="49485-148">$TIME</span><span class="sxs-lookup"><span data-stu-id="49485-148">$TIME</span></span>|<span data-ttu-id="49485-149">Betrag</span><span class="sxs-lookup"><span data-stu-id="49485-149">Amount</span></span>|  
|-----------|------------|  
|<span data-ttu-id="49485-150">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-150">7/25/2008</span></span>|<span data-ttu-id="49485-151">99978,00</span><span class="sxs-lookup"><span data-stu-id="49485-151">99978.00</span></span>|  
|<span data-ttu-id="49485-152">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-152">8/25/2008</span></span>|<span data-ttu-id="49485-153">145575,07</span><span class="sxs-lookup"><span data-stu-id="49485-153">145575.07</span></span>|  
|<span data-ttu-id="49485-154">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-154">9/25/2008</span></span>|<span data-ttu-id="49485-155">116835,19</span><span class="sxs-lookup"><span data-stu-id="49485-155">116835.19</span></span>|  
|<span data-ttu-id="49485-156">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-156">10/25/2008</span></span>|<span data-ttu-id="49485-157">116537,38</span><span class="sxs-lookup"><span data-stu-id="49485-157">116537.38</span></span>|  
|<span data-ttu-id="49485-158">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-158">11/25/2008</span></span>|<span data-ttu-id="49485-159">107760,55</span><span class="sxs-lookup"><span data-stu-id="49485-159">107760.55</span></span>|  
  
 <span data-ttu-id="49485-160">**M200 Europe-prätmenge**</span><span class="sxs-lookup"><span data-stu-id="49485-160">**M200 Europe PredictQuantity**</span></span>  
  
|<span data-ttu-id="49485-161">$TIME</span><span class="sxs-lookup"><span data-stu-id="49485-161">$TIME</span></span>|<span data-ttu-id="49485-162">Menge</span><span class="sxs-lookup"><span data-stu-id="49485-162">Quantity</span></span>|  
|-----------|--------------|  
|<span data-ttu-id="49485-163">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-163">7/25/2008</span></span>|<span data-ttu-id="49485-164">52</span><span class="sxs-lookup"><span data-stu-id="49485-164">52</span></span>|  
|<span data-ttu-id="49485-165">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-165">8/25/2008</span></span>|<span data-ttu-id="49485-166">67</span><span class="sxs-lookup"><span data-stu-id="49485-166">67</span></span>|  
|<span data-ttu-id="49485-167">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-167">9/25/2008</span></span>|<span data-ttu-id="49485-168">58</span><span class="sxs-lookup"><span data-stu-id="49485-168">58</span></span>|  
|<span data-ttu-id="49485-169">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-169">10/25/2008</span></span>|<span data-ttu-id="49485-170">57</span><span class="sxs-lookup"><span data-stu-id="49485-170">57</span></span>|  
|<span data-ttu-id="49485-171">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-171">11/25/2008</span></span>|<span data-ttu-id="49485-172">54</span><span class="sxs-lookup"><span data-stu-id="49485-172">54</span></span>|  
  
 <span data-ttu-id="49485-173">**M200 Nordamerika-prätamount**</span><span class="sxs-lookup"><span data-stu-id="49485-173">**M200 North America - PredictAmount**</span></span>  
  
|<span data-ttu-id="49485-174">$TIME</span><span class="sxs-lookup"><span data-stu-id="49485-174">$TIME</span></span>|<span data-ttu-id="49485-175">Betrag</span><span class="sxs-lookup"><span data-stu-id="49485-175">Amount</span></span>|  
|-----------|------------|  
|<span data-ttu-id="49485-176">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-176">7/25/2008</span></span>|<span data-ttu-id="49485-177">348533,93</span><span class="sxs-lookup"><span data-stu-id="49485-177">348533.93</span></span>|  
|<span data-ttu-id="49485-178">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-178">8/25/2008</span></span>|<span data-ttu-id="49485-179">340097,98</span><span class="sxs-lookup"><span data-stu-id="49485-179">340097.98</span></span>|  
|<span data-ttu-id="49485-180">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-180">9/25/2008</span></span>|<span data-ttu-id="49485-181">257986,19</span><span class="sxs-lookup"><span data-stu-id="49485-181">257986.19</span></span>|  
|<span data-ttu-id="49485-182">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-182">10/25/2008</span></span>|<span data-ttu-id="49485-183">374658,24</span><span class="sxs-lookup"><span data-stu-id="49485-183">374658.24</span></span>|  
|<span data-ttu-id="49485-184">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-184">11/25/2008</span></span>|<span data-ttu-id="49485-185">379241,44</span><span class="sxs-lookup"><span data-stu-id="49485-185">379241.44</span></span>|  
  
 <span data-ttu-id="49485-186">**M200 Nordamerika-prätmenge**</span><span class="sxs-lookup"><span data-stu-id="49485-186">**M200 North America - PredictQuantity**</span></span>  
  
|<span data-ttu-id="49485-187">$TIME</span><span class="sxs-lookup"><span data-stu-id="49485-187">$TIME</span></span>|<span data-ttu-id="49485-188">Menge</span><span class="sxs-lookup"><span data-stu-id="49485-188">Quantity</span></span>|  
|-----------|--------------|  
|<span data-ttu-id="49485-189">7/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-189">7/25/2008</span></span>|<span data-ttu-id="49485-190">272</span><span class="sxs-lookup"><span data-stu-id="49485-190">272</span></span>|  
|<span data-ttu-id="49485-191">8/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-191">8/25/2008</span></span>|<span data-ttu-id="49485-192">152</span><span class="sxs-lookup"><span data-stu-id="49485-192">152</span></span>|  
|<span data-ttu-id="49485-193">9/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-193">9/25/2008</span></span>|<span data-ttu-id="49485-194">250</span><span class="sxs-lookup"><span data-stu-id="49485-194">250</span></span>|  
|<span data-ttu-id="49485-195">10/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-195">10/25/2008</span></span>|<span data-ttu-id="49485-196">181</span><span class="sxs-lookup"><span data-stu-id="49485-196">181</span></span>|  
|<span data-ttu-id="49485-197">11/25/2008</span><span class="sxs-lookup"><span data-stu-id="49485-197">11/25/2008</span></span>|<span data-ttu-id="49485-198">290</span><span class="sxs-lookup"><span data-stu-id="49485-198">290</span></span>|  
  
> [!WARNING]  
>  <span data-ttu-id="49485-199">Die in der Beispieldatenbank verwendeten Datumsangaben wurden für diese Version geändert.</span><span class="sxs-lookup"><span data-stu-id="49485-199">The dates that are used in the sample database have changed for this release.</span></span> <span data-ttu-id="49485-200">Wenn Sie eine frühere Version der Beispieldaten verwenden, können sich abweichende Ergebnisse ergeben.</span><span class="sxs-lookup"><span data-stu-id="49485-200">If you are using an earlier version of the sample data, you might see different results.</span></span>  
  
## <a name="saving-the-prediction-results"></a><span data-ttu-id="49485-201">Speichern der Vorhersageergebnisse</span><span class="sxs-lookup"><span data-stu-id="49485-201">Saving the Prediction Results</span></span>  
 <span data-ttu-id="49485-202">Sie können die Vorhersageergebnisse auf unterschiedlichste Weise nutzen.</span><span class="sxs-lookup"><span data-stu-id="49485-202">You have several different options for using the prediction results.</span></span> <span data-ttu-id="49485-203">So können Sie beispielsweise die Ergebnisse vereinfachen und die Daten aus der Ergebnisansicht kopieren und in ein Excel-Arbeitsblatt oder in eine andere Datei einfügen.</span><span class="sxs-lookup"><span data-stu-id="49485-203">You can flatten the results, copy the data from the Results view, and paste it into an Excel worksheet or other file.</span></span>  
  
 <span data-ttu-id="49485-204">Um den Prozess der Ergebnisspeicherung zu vereinfachen, bietet der Data Mining-Designer auch die Möglichkeit, die Daten in einer Datenquellensicht zu speichern.</span><span class="sxs-lookup"><span data-stu-id="49485-204">To simplify the process of saving results, Data Mining Designer also provides the ability to save the data to a data source view.</span></span> <span data-ttu-id="49485-205">Die Funktionalität zum Speichern von Ergebnissen in einer Datenquellensicht ist nur in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] verfügbar.</span><span class="sxs-lookup"><span data-stu-id="49485-205">The functionality for saving results to a data source view is available only in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="49485-206">Die Ergebnisse können nur in einem vereinfachten Format gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="49485-206">The results can only be stored in a flattened format.</span></span>  
  
#### <a name="to-flatten-the-results-in-the-results-pane"></a><span data-ttu-id="49485-207">So vereinfachen Sie die Ergebnisse im Ergebnisbereich</span><span class="sxs-lookup"><span data-stu-id="49485-207">To flatten the results in the Results pane</span></span>  
  
1.  <span data-ttu-id="49485-208">Klicken Sie im Abfrage-Generator Vorhersage auf **zur Abfrage Entwurfs Sicht wechseln**.</span><span class="sxs-lookup"><span data-stu-id="49485-208">In the Prediction Query Builder, click **Switch to query design view**.</span></span>  
  
     <span data-ttu-id="49485-209">Die Sicht wird geändert, und Sie können den Text der DMX-Abfrage manuell bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="49485-209">The view changes to allow manual editing of the DMX query text.</span></span>  
  
2.  <span data-ttu-id="49485-210">Geben Sie das `FLATTENED`-Schlüsselwort nach dem `SELECT`-Schlüsselwort ein.</span><span class="sxs-lookup"><span data-stu-id="49485-210">Type the `FLATTENED` keyword after the `SELECT` keyword.</span></span> <span data-ttu-id="49485-211">Der vollständige Abfragetext sollte wie folgt lauten:</span><span class="sxs-lookup"><span data-stu-id="49485-211">The complete query text should be as follows:</span></span>  
  
    ```  
    SELECT FLATTENED  
      [Forecasting].[Model Region],  
      (PredictTimeSeries([Forecasting].[Amount],5)) as [PredictAmount],  
      (PredictTimeSeries([Forecasting].[Quantity],5)) as [PredictQuantity]  
    FROM  
      [Forecasting]  
    ```  
  
3.  <span data-ttu-id="49485-212">Optional können Sie eine Klausel zum Einschränken der Ergebnisse eingeben. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="49485-212">Optionally, you can type a clause to restrict the results, such as the following example:</span></span>  
  
    ```  
    SELECT FLATTENED  
      [Forecasting].[Model Region],  
      (PredictTimeSeries([Forecasting].[Amount],5)) as [PredictAmount],  
      (PredictTimeSeries([Forecasting].[Quantity],5)) as [PredictQuantity]  
    FROM  
      [Forecasting]  
    WHERE [Forecasting].[Model Region] = 'M200 North America'   
    OR [Forecasting].[Model Region] = 'M200 Europe'  
  
    ```  
  
4.  <span data-ttu-id="49485-213">Klicken Sie **auf zur Abfrageergebnis Sicht wechseln**.</span><span class="sxs-lookup"><span data-stu-id="49485-213">Click **Switch to query result view**.</span></span>  
  
#### <a name="to-export-prediction-query-results"></a><span data-ttu-id="49485-214">So exportieren Sie Ergebnisse von Vorhersageabfragen</span><span class="sxs-lookup"><span data-stu-id="49485-214">To export prediction query results</span></span>  
  
1.  <span data-ttu-id="49485-215">Klicken Sie auf **Abfrageergebnisse speichern**.</span><span class="sxs-lookup"><span data-stu-id="49485-215">Click **Save query results**.</span></span>  
  
2.  <span data-ttu-id="49485-216">Wählen Sie im Dialogfeld **Ergebnis der Data Mining-Abfrage speichern** für **Datenquelle**die Option aus [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49485-216">In the **Save Data Mining Query Result** dialog box, for **Data Source**, select [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)].</span></span> <span data-ttu-id="49485-217">Wenn Sie die Daten in einer anderen relationalen Datenbank speichern möchten, können Sie auch eine Datenquelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="49485-217">You can also create a data source if you want to save the data to a different relational database.</span></span>  
  
3.  <span data-ttu-id="49485-218">Geben Sie in der Spalte **Tabellenname** einen neuen temporären Tabellennamen ein, z. b. **Test Vorhersagen**.</span><span class="sxs-lookup"><span data-stu-id="49485-218">In the **Table Name** column, type a new temporary table name, such as **Test Predictions**.</span></span>  
  
4.  <span data-ttu-id="49485-219">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="49485-219">Click **Save**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="49485-220">Stellen Sie eine Verbindung zur Instanz der Datenbank-Engine her, in der Sie die Daten gespeichert haben, und erstellen Sie eine Abfrage, um die Tabelle anzuzeigen, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="49485-220">To view the table that you created, create a connection to the database engine of the instance where you saved the data, and create a query.</span></span>  
  
## <a name="conclusion"></a><span data-ttu-id="49485-221">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="49485-221">Conclusion</span></span>  
 <span data-ttu-id="49485-222">Sie können nun ein grundlegendes Zeitreihenmodell erstellen, Prognosen interpretieren und Vorhersagen erstellen.</span><span class="sxs-lookup"><span data-stu-id="49485-222">You have learned how to build a basic time series model, interpret the forecasts, and create predictions.</span></span>  
  
 <span data-ttu-id="49485-223">Die verbleibenden Aufgaben in diesem Lernprogramm sind optional und beschreiben erweiterte Zeitreihenvorhersagen.</span><span class="sxs-lookup"><span data-stu-id="49485-223">The remaining tasks in this tutorial are optional, and describe advanced time series predictions.</span></span> <span data-ttu-id="49485-224">Wenn Sie dieses Thema weiter verfolgen, lernen Sie, wie Sie dem Modell neue Daten hinzufügen und Vorhersagen zur erweiterten Reihe erstellen können.</span><span class="sxs-lookup"><span data-stu-id="49485-224">If you decide to go on, you will learn how to add new data to your model and create predictions on the extended series.</span></span> <span data-ttu-id="49485-225">Sie lernen zudem, Kreuzvorhersagen durchzuführen, indem Sie den Trend im Modell verwenden und die Daten durch eine neue Datenreihe ersetzen.</span><span class="sxs-lookup"><span data-stu-id="49485-225">You will also learn how to perform cross-prediction, by using the trend in the model but replacing the data with a new series of data.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="49485-226">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="49485-226">Next Lesson</span></span>  
 [<span data-ttu-id="49485-227">Erweiterte Zeitreihen Vorhersagen &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="49485-227">Advanced Time Series Predictions &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/advanced-time-series-predictions-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="49485-228">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="49485-228">See Also</span></span>  
 [<span data-ttu-id="49485-229">Abfragebeispiel Zeitreihenmodell</span><span class="sxs-lookup"><span data-stu-id="49485-229">Time Series Model Query Examples</span></span>](../../2014/analysis-services/data-mining/time-series-model-query-examples.md)  
  
  
