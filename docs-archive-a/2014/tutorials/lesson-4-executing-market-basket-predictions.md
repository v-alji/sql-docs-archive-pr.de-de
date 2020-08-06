---
title: 'Lektion 4: Ausführen von Market Basket-Vorhersagen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b3238f1b-ea04-4253-ade2-838a806b62fe
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 3b49fc242eb8b2242269c5af33cc094937bbe0de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616874"
---
# <a name="lesson-4-executing-market-basket-predictions"></a><span data-ttu-id="603a1-102">Lektion 4: Ausführen von Warenkorbvorhersagen</span><span class="sxs-lookup"><span data-stu-id="603a1-102">Lesson 4: Executing Market Basket Predictions</span></span>
  <span data-ttu-id="603a1-103">In dieser Lektion verwenden Sie die DMX- `SELECT` Anweisung, um Vorhersagen basierend auf den Zuordnungs Modellen zu erstellen, die Sie in [Lektion 2: Hinzufügen von Mining Modellen zur Market Basket-Mining Struktur](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md)erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="603a1-103">In this lesson, you will use the DMX `SELECT` statement to create predictions based on the association models you created in [Lesson 2: Adding Mining Models to the Market Basket Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span></span> <span data-ttu-id="603a1-104">Eine Vorhersageabfrage wird unter Verwendung der DMX `SELECT`-Anweisung unter Hinzufügung einer `PREDICTION JOIN`-Klausel erstellt.</span><span class="sxs-lookup"><span data-stu-id="603a1-104">A prediction query is created by using the DMX `SELECT` statement and adding a `PREDICTION JOIN` clause.</span></span> <span data-ttu-id="603a1-105">Weitere Informationen zur Syntax eines Vorhersage Joins finden [Sie unter Select from &#60;Model&#62; Vorhersage Join &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx).</span><span class="sxs-lookup"><span data-stu-id="603a1-105">For more information about the syntax of a prediction join, see [SELECT FROM &#60;model&#62; PREDICTION JOIN &#40;DMX&#41;](/sql/dmx/select-from-model-cases-dmx).</span></span>  
  
 <span data-ttu-id="603a1-106">Das Formular **Select from \<model> Vorhersage Join** der `SELECT` Anweisung enthält drei Teile:</span><span class="sxs-lookup"><span data-stu-id="603a1-106">The **SELECT FROM \<model> PREDICTION JOIN** form of the `SELECT` statement contains three parts:</span></span>  
  
-   <span data-ttu-id="603a1-107">Einer Liste der Miningmodellspalten und Vorhersagefunktionen, die im Resultset zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="603a1-107">A list of the mining model columns and prediction functions that are returned in the result set.</span></span> <span data-ttu-id="603a1-108">Diese Liste kann auch Eingabespalten aus den Quelldaten enthalten.</span><span class="sxs-lookup"><span data-stu-id="603a1-108">This list can also contain input columns from the source data.</span></span>  
  
-   <span data-ttu-id="603a1-109">Eine Quellabfrage, die die zum Erstellen einer Vorhersage verwendeten Daten definiert.</span><span class="sxs-lookup"><span data-stu-id="603a1-109">A source query that defines the data that is being used to create a prediction.</span></span> <span data-ttu-id="603a1-110">Wenn Sie beispielsweise zahlreiche Vorhersagen in einem Batch erstellen, kann die Quellabfrage eine Liste von Kunden abrufen.</span><span class="sxs-lookup"><span data-stu-id="603a1-110">For example, if you are creating many predictions in a batch, the source query could retrieve a list of customers.</span></span>  
  
-   <span data-ttu-id="603a1-111">Einer Zuordnung von Miningmodellspalten und Quelldaten.</span><span class="sxs-lookup"><span data-stu-id="603a1-111">A mapping between the mining model columns and the source data.</span></span> <span data-ttu-id="603a1-112">Wenn die Namen der Spalten übereinstimmen, können Sie die `NATURAL PREDICTION JOIN`-Syntax verwenden und auf die Spaltenzuordnungen verzichten.</span><span class="sxs-lookup"><span data-stu-id="603a1-112">If the columns names match, you can use the `NATURAL PREDICTION JOIN` syntax and omit the column mappings.</span></span>  
  
 <span data-ttu-id="603a1-113">Mithilfe von Vorhersagefunktionen lässt sich die Abfrage optimieren.</span><span class="sxs-lookup"><span data-stu-id="603a1-113">You can enhance the query by using prediction functions.</span></span> <span data-ttu-id="603a1-114">Vorhersagefunktionen stellen zusätzliche Informationen bereit, z. B. die Wahrscheinlichkeit des Eintreffens einer Vorhersage oder die Unterstützung für die Vorhersage im Trainingsdataset.</span><span class="sxs-lookup"><span data-stu-id="603a1-114">Prediction functions provide additional information, such as the probability of a prediction occurring, or the support for a prediction in the training dataset.</span></span> <span data-ttu-id="603a1-115">Weitere Informationen zu Vorhersagefunktionen finden Sie unter [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span><span class="sxs-lookup"><span data-stu-id="603a1-115">For more information about prediction functions, see [Functions &#40;DMX&#41;](/sql/dmx/functions-dmx).</span></span>  
  
 <span data-ttu-id="603a1-116">Vorhersageabfragen können auch mit dem Generator für Vorhersageabfragen in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="603a1-116">You can also use the prediction query builder in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to create prediction queries.</span></span>  
  
## <a name="singleton-prediction-join-statement"></a><span data-ttu-id="603a1-117">PREDICTION JOIN-Anweisung in einer SINGLETON-Vorhersageabfrage</span><span class="sxs-lookup"><span data-stu-id="603a1-117">Singleton PREDICTION JOIN Statement</span></span>  
 <span data-ttu-id="603a1-118">Der erste Schritt besteht darin, eine SINGLETON-Abfrage zu erstellen, indem Sie die Syntax **Select from \<model> Vorhersage Join** verwenden und einen einzelnen Satz von Werten als Eingabe bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="603a1-118">The first step is to create a singleton query, by using the **SELECT FROM \<model> PREDICTION JOIN** syntax and supplying a single set of values as input.</span></span> <span data-ttu-id="603a1-119">Es folgt ein allgemeines Beispiel für die SINGLETON-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="603a1-119">The following is a generic example of the singleton statement:</span></span>  
  
```  
SELECT <select list>  
    FROM [<mining model>]   
[NATURAL] PREDICTION JOIN  
(SELECT '<value>' AS [<column>],   
    (SELECT 'value' AS [<nested column>] UNION  
        SELECT 'value' AS [<nested column>] ...)   
    AS [<nested table>])  
AS [<input alias>]  
```  
  
 <span data-ttu-id="603a1-120">In der ersten Codezeile werden die Spalten des Miningmodells definiert, das die Abfrage zurückgibt und der Name des Miningmodells angegeben, mit dem die Vorhersage generiert wurde:</span><span class="sxs-lookup"><span data-stu-id="603a1-120">The first line of the code defines the columns from the mining model that the query returns, and specifies the name of the mining model used to generate the prediction:</span></span>  
  
```  
SELECT <select list> FROM [<mining model>]   
```  
  
 <span data-ttu-id="603a1-121">In der nächsten Zeile des Codes wird der auszuführende Vorgang angegeben.</span><span class="sxs-lookup"><span data-stu-id="603a1-121">The next line of the code indicates the operation to perform.</span></span> <span data-ttu-id="603a1-122">Da Sie Werte für jede der Spalten angeben und die Namen genauso eingeben, dass sie mit dem Modell übereinstimmen, können Sie die `NATURAL PREDICTION JOIN`-Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="603a1-122">Because you will specify values for each of the columns and type the column names exactly so as to match the model, you can use the `NATURAL PREDICTION JOIN` syntax.</span></span> <span data-ttu-id="603a1-123">Wenn die Spaltennamen jedoch anders lauten, müssen Sie Zuordnungen zwischen den Spalten im Modell und den Spalten in den neuen Daten angeben, indem Sie eine `ON`-Klausel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="603a1-123">However, if the column names were different, you would have to specify mappings between the columns in the model and the columns in the new data by adding an `ON` clause.</span></span>  
  
```  
[NATURAL] PREDICTION JOIN  
```  
  
 <span data-ttu-id="603a1-124">Die nächsten Codezeilen definieren die Produkte im Einkaufswagen, die zum Vorhersagen zusätzlicher Produkte, die ein Kunde erwerben wird, verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="603a1-124">The next lines of the code define the products in the shopping cart that will be used to predict additional products that a customer will add:</span></span>  
  
```  
(SELECT '<value>' AS [<column>],   
    (SELECT 'value' AS [<nested column>] UNION  
        SELECT 'value' AS [<nested column>] ...)   
    AS [<nested table>])  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="603a1-125">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="603a1-125">Lesson Tasks</span></span>  
 <span data-ttu-id="603a1-126">Im Rahmen dieser Lektion führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="603a1-126">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="603a1-127">Erstellen Sie eine Abfrage, mit der vorhergesagt wird, welche anderen Elemente ein Kunde wahrscheinlich kaufen wird. Dies geschieht auf der Grundlage vorhandener Elemente in Ihrem Warenkorb.</span><span class="sxs-lookup"><span data-stu-id="603a1-127">Create a query that predicts what other items a customer will likely purchase, based on items already existing in their shopping cart.</span></span> <span data-ttu-id="603a1-128">Sie erstellen diese Abfrage, indem Sie das Mining Modell mit dem Standard *MINIMUM_PROBABILITY*verwenden.</span><span class="sxs-lookup"><span data-stu-id="603a1-128">You will create this query by using the mining model with the default *MINIMUM_PROBABILITY*.</span></span>  
  
-   <span data-ttu-id="603a1-129">Erstellen einer Abfrage, die anhand von Artikeln, die sich bereits im Einkaufswagen eines Kunden befinden, vorhersagt, welche anderen Artikel ein Kunde wahrscheinlich kaufen wird.</span><span class="sxs-lookup"><span data-stu-id="603a1-129">Create a query that predicts what other items a customer will likely purchase based on items already existing in their shopping cart.</span></span> <span data-ttu-id="603a1-130">Diese Abfrage basiert auf einem anderen Modell, in dem *MINIMUM_PROBABILITY* auf 0,01 festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="603a1-130">This query is based on a different model, in which *MINIMUM_PROBABILITY* has been set to 0.01.</span></span> <span data-ttu-id="603a1-131">Da der Standardwert für *MINIMUM_PROBABILITY* in Zuordnungs Modellen 0,3 ist, sollte die Abfrage für dieses Modell mehr mögliche Elemente als die Abfrage für das Standardmodell zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="603a1-131">Because the default value for *MINIMUM_PROBABILITY* in association models is 0.3, the query on this model should return more possible items than the query on the default model.</span></span>  
  
## <a name="create-a-prediction-by-using-a-model-with-the-default-minimum_probability"></a><span data-ttu-id="603a1-132">Erstellen einer Vorhersage durch Verwenden eines Modells mit dem MINIMUM_PROBABILITY-Standardwert</span><span class="sxs-lookup"><span data-stu-id="603a1-132">Create a Prediction by Using a Model with the Default MINIMUM_PROBABILITY</span></span>  
  
#### <a name="to-create-an-association-query"></a><span data-ttu-id="603a1-133">So erstellen Sie eine Zuordnungsabfrage</span><span class="sxs-lookup"><span data-stu-id="603a1-133">To create an association query</span></span>  
  
1.  <span data-ttu-id="603a1-134">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX** , um den Abfrage-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="603a1-134">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="603a1-135">Kopieren Sie das Standardbeispiel der `PREDICTION JOIN`-Anweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="603a1-135">Copy the generic example of the `PREDICTION JOIN` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="603a1-136">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="603a1-136">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="603a1-137">durch:</span><span class="sxs-lookup"><span data-stu-id="603a1-137">with:</span></span>  
  
    ```  
    PREDICT([Default Association].[Products],INCLUDE_STATISTICS,3)  
    ```  
  
     <span data-ttu-id="603a1-138">Sie können einfach den Spaltennamen [Products] einschließen, aber mithilfe der [Vorhersage &#40;DMX-&#41;](/sql/dmx/predict-dmx) Funktion können Sie die Anzahl der vom Algorithmus zurückgegebenen Produkte auf drei begrenzen.</span><span class="sxs-lookup"><span data-stu-id="603a1-138">You could just include the column name [Products], but by using the [Predict &#40;DMX&#41;](/sql/dmx/predict-dmx) function, you can limit the number of products that are returned by the algorithm to three.</span></span> <span data-ttu-id="603a1-139">Sie können auch `INCLUDE_STATISTICS` verwenden. Damit werden der Unterstützungswert, die Wahrscheinlichkeit und die angepasste Wahrscheinlichkeit für jedes Produkt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="603a1-139">You can also use `INCLUDE_STATISTICS`, which returns the support, probability, and adjusted probability for each product.</span></span> <span data-ttu-id="603a1-140">Mithilfe dieser statistischen Informationen können Sie die Genauigkeit der Vorhersage bewerten.</span><span class="sxs-lookup"><span data-stu-id="603a1-140">These statistics help you rate the accuracy of the prediction.</span></span>  
  
4.  <span data-ttu-id="603a1-141">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="603a1-141">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="603a1-142">durch:</span><span class="sxs-lookup"><span data-stu-id="603a1-142">with:</span></span>  
  
    ```  
    [Default Association]  
    ```  
  
5.  <span data-ttu-id="603a1-143">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="603a1-143">Replace the following:</span></span>  
  
    ```  
    (SELECT '<value>' AS [<column>],   
        (SELECT 'value' AS [<nested column>] UNION  
            SELECT 'value' AS [<nested column>] ...)   
        AS [<nested table>])  
    ```  
  
     <span data-ttu-id="603a1-144">durch:</span><span class="sxs-lookup"><span data-stu-id="603a1-144">with:</span></span>  
  
    ```  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
     <span data-ttu-id="603a1-145">Diese Anweisung verwendet die `UNION`-Anweisung, um drei Produkte anzugeben, die zusammen mit den vorhergesagten Produkten im Einkaufskorb enthalten sein müssen.</span><span class="sxs-lookup"><span data-stu-id="603a1-145">This statement uses the `UNION` statement to specify three products that must be included in the shopping cart together with the predicted products.</span></span> <span data-ttu-id="603a1-146">Die Modell-Spalte in der `SELECT`-Anweisung entspricht der Modell-Spalte, die in der geschachtelten Products-Tabelle enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="603a1-146">The Model column in the `SELECT` statement corresponds to the model column that is contained in the nested products table.</span></span>  
  
     <span data-ttu-id="603a1-147">Die gesamte Anweisung sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="603a1-147">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
      PREDICT([Default Association].[Products],INCLUDE_STATISTICS,3)  
    From  
      [Default Association]  
    NATURAL PREDICTION JOIN  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
6.  <span data-ttu-id="603a1-148">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="603a1-148">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="603a1-149">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `Association Prediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="603a1-149">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Association Prediction.dmx`.</span></span>  
  
8.  <span data-ttu-id="603a1-150">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="603a1-150">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="603a1-151">Die Abfrage gibt eine Tabelle zurück, die drei Produkte enthält: HL Mountain Tire, Fender Set - Mountain und ML Mountain Tire.</span><span class="sxs-lookup"><span data-stu-id="603a1-151">The query returns a table that contains three products: HL Mountain Tire, Fender Set - Mountain, and ML Mountain Tire.</span></span> <span data-ttu-id="603a1-152">In der Tabelle werden diese zurückgegebenen Produkte in der Reihenfolge ihrer Wahrscheinlichkeit aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="603a1-152">The table lists these returned products in order of probability.</span></span> <span data-ttu-id="603a1-153">Das zurückgegebene Produkt, dessen Wahrscheinlichkeit, zusammen mit den in der Abfrage angegebenen drei Produkten in den gleichen Warenkorb eingefügt zu werden, am höchsten ist, wird an der Spitze der Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="603a1-153">The returned product that is most likely to be included in the same shopping cart as the three products specified in the query appears at the top of the table.</span></span> <span data-ttu-id="603a1-154">Die folgenden zwei Produkte besitzen die nächsthöhere Wahrscheinlichkeit, in den Warenkorb eingefügt zu werden.</span><span class="sxs-lookup"><span data-stu-id="603a1-154">The two products that follow are the next most likely to be included in the shopping cart.</span></span> <span data-ttu-id="603a1-155">Die Tabelle enthält zudem statistische Informationen, die die Genauigkeit der Vorhersage beschreiben.</span><span class="sxs-lookup"><span data-stu-id="603a1-155">The table also contains statistics describing the accuracy of the prediction.</span></span>  
  
## <a name="create-a-prediction-by-using-a-model-with-a-minimum_probability-of-001"></a><span data-ttu-id="603a1-156">Erstellen einer Vorhersage durch Verwenden eines Modells mit dem MINIMUM_PROBABILITY-Wert 0,01</span><span class="sxs-lookup"><span data-stu-id="603a1-156">Create a Prediction by Using a Model with a MINIMUM_PROBABILITY of 0.01</span></span>  
  
#### <a name="to-create-an-association-query"></a><span data-ttu-id="603a1-157">So erstellen Sie eine Zuordnungsabfrage</span><span class="sxs-lookup"><span data-stu-id="603a1-157">To create an association query</span></span>  
  
1.  <span data-ttu-id="603a1-158">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX** , um den Abfrage-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="603a1-158">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open the Query Editor.</span></span>  
  
2.  <span data-ttu-id="603a1-159">Kopieren Sie das Standardbeispiel der `PREDICTION JOIN`-Anweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="603a1-159">Copy the generic example of the `PREDICTION JOIN` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="603a1-160">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="603a1-160">Replace the following:</span></span>  
  
    ```  
    <select list>   
    ```  
  
     <span data-ttu-id="603a1-161">durch:</span><span class="sxs-lookup"><span data-stu-id="603a1-161">with:</span></span>  
  
    ```  
    PREDICT([Modified Association].[Products],INCLUDE_STATISTICS,3)  
    ```  
  
4.  <span data-ttu-id="603a1-162">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="603a1-162">Replace the following:</span></span>  
  
    ```  
    [<mining model>]   
    ```  
  
     <span data-ttu-id="603a1-163">durch:</span><span class="sxs-lookup"><span data-stu-id="603a1-163">with:</span></span>  
  
    ```  
    [Modified Association]  
    ```  
  
5.  <span data-ttu-id="603a1-164">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="603a1-164">Replace the following:</span></span>  
  
    ```  
    (SELECT '<value>' AS [<column>],   
        (SELECT 'value' AS [<nested column>] UNION  
            SELECT 'value' AS [<nested column>] ...)   
        AS [<nested table>])  
    ```  
  
     <span data-ttu-id="603a1-165">durch:</span><span class="sxs-lookup"><span data-stu-id="603a1-165">with:</span></span>  
  
    ```  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
     <span data-ttu-id="603a1-166">Diese Anweisung verwendet die `UNION`-Anweisung, um drei Produkte anzugeben, die zusammen mit den vorhergesagten Produkten im Einkaufskorb enthalten sein müssen.</span><span class="sxs-lookup"><span data-stu-id="603a1-166">This statement uses the `UNION` statement to specify three products that must be included in the shopping cart together with the predicted products.</span></span> <span data-ttu-id="603a1-167">Die `[Model]`-Spalte in der `SELECT`-Anweisung entspricht der Spalte, die in der geschachtelten Products-Tabelle enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="603a1-167">The `[Model]` column in the `SELECT` statement corresponds to the column in the nested products table.</span></span>  
  
     <span data-ttu-id="603a1-168">Die gesamte Anweisung sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="603a1-168">The complete statement should now be as follows:</span></span>  
  
    ```  
    SELECT  
      PREDICT([Modified Association].[Products],INCLUDE_STATISTICS,3)  
    From  
      [Modified Association]  
    NATURAL PREDICTION JOIN  
    (SELECT (SELECT 'Mountain Bottle Cage' AS [Model]  
      UNION SELECT 'Mountain Tire Tube' AS [Model]  
      UNION SELECT 'Mountain-200' AS [Model]) AS [Products]) AS t  
    ```  
  
6.  <span data-ttu-id="603a1-169">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="603a1-169">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="603a1-170">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `Modified Association Prediction.dmx` .</span><span class="sxs-lookup"><span data-stu-id="603a1-170">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Modified Association Prediction.dmx`.</span></span>  
  
8.  <span data-ttu-id="603a1-171">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="603a1-171">On the toolbar, click the **Execute** button.</span></span>  
  
     <span data-ttu-id="603a1-172">Die Abfrage gibt eine Tabelle zurück, die drei Produkte enthält: HL Mountain Tire, Water Bottle und Fender Set - Mountain.</span><span class="sxs-lookup"><span data-stu-id="603a1-172">The query returns a table that contains three products: HL Mountain Tire, Water Bottle, and Fender Set - Mountain.</span></span> <span data-ttu-id="603a1-173">In der Tabelle werden diese Produkte in der Reihenfolge ihrer Wahrscheinlichkeit aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="603a1-173">The table lists these products in order of probability.</span></span> <span data-ttu-id="603a1-174">Das Produkt, das an der Spitze der Tabelle angezeigt wird, besitzt die höchste Wahrscheinlichkeit, zusammen mit den in der Abfrage angegebenen drei Produkten in den gleichen Warenkorb eingefügt zu werden.</span><span class="sxs-lookup"><span data-stu-id="603a1-174">The product that appears at the top of the table is the product that is most likely to be included in the same shopping cart as the three products specified in the query.</span></span> <span data-ttu-id="603a1-175">Die restlichen Produkte besitzen die nächsthöhere Wahrscheinlichkeit, in den Warenkorb eingefügt zu werden.</span><span class="sxs-lookup"><span data-stu-id="603a1-175">The remaining products are the next most likely to be included in the shopping cart.</span></span> <span data-ttu-id="603a1-176">Die Tabelle enthält auch Statistiken, die die Genauigkeit der Vorhersage beschreiben.</span><span class="sxs-lookup"><span data-stu-id="603a1-176">The table also contains statistics that describe the accuracy of the prediction.</span></span>  
  
     <span data-ttu-id="603a1-177">Sie können in den Ergebnissen dieser Abfrage erkennen, dass der Wert des *MINIMUM_PROBABILITY* -Parameters die von der Abfrage zurückgegebenen Ergebnisse beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="603a1-177">You can see from the results of this query that the value of the *MINIMUM_PROBABILITY* parameter affects the results returned by the query.</span></span>  
  
 <span data-ttu-id="603a1-178">Dies ist der letzte Schritt im Market Basket-Lernprogramm.</span><span class="sxs-lookup"><span data-stu-id="603a1-178">This is the last step in the Market Basket tutorial.</span></span> <span data-ttu-id="603a1-179">Sie verfügen jetzt über einen Satz von Modellen, mit dem sich vorhersagen lässt, welche Produkte von Kunden möglicherweise gleichzeitig gekauft werden.</span><span class="sxs-lookup"><span data-stu-id="603a1-179">You now have a set of models that you can use to predict the products that customers might purchase at the same time.</span></span>  
  
 <span data-ttu-id="603a1-180">Informationen zur Verwendung von DMX in einem anderen Vorhersage Szenario finden Sie unter [Bike Buyer DMX Tutorial](../../2014/tutorials/bike-buyer-dmx-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="603a1-180">To learn how to use DMX in another predictive scenario, see [Bike Buyer DMX Tutorial](../../2014/tutorials/bike-buyer-dmx-tutorial.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="603a1-181">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="603a1-181">See Also</span></span>  
 <span data-ttu-id="603a1-182">[Beispiele für Zuordnungs Modell Abfragen](../../2014/analysis-services/data-mining/association-model-query-examples.md) </span><span class="sxs-lookup"><span data-stu-id="603a1-182">[Association Model Query Examples](../../2014/analysis-services/data-mining/association-model-query-examples.md) </span></span>  
 [<span data-ttu-id="603a1-183">Schnittstellen für Data Mining-Abfragen</span><span class="sxs-lookup"><span data-stu-id="603a1-183">Data Mining Query Interfaces</span></span>](../../2014/analysis-services/data-mining/data-mining-query-tools.md)  
  
  
