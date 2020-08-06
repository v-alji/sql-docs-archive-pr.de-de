---
title: 'Lektion 2: Hinzufügen von Mining Modellen zur Bike Buyer-Mining Struktur | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 03fe44c5-6452-4ed0-95f6-9682670c0f52
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: de65fb7a85154f607cd8f266faec4621cdc41476
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717107"
---
# <a name="lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure"></a><span data-ttu-id="20760-102">Lektion 2: Hinzufügen von Miningmodellen zur Bike Buyer-Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="20760-102">Lesson 2: Adding Mining Models to the Bike Buyer Mining Structure</span></span>
  <span data-ttu-id="20760-103">In dieser Lektion fügen Sie der Bike Buyer-Mining Struktur, die Sie [Lektion 1: Erstellen der Bike Buyer-Mining Struktur](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md)erstellt haben, zwei Mining Modelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="20760-103">In this lesson, you will add two mining models to the Bike Buyer mining structure that you created [Lesson 1: Creating the Bike Buyer Mining Structure](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md).</span></span> <span data-ttu-id="20760-104">Diese Miningmodelle ermöglichen es Ihnen, mit einem Modell die Daten zu prüfen und mit einem anderen Vorhersagen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="20760-104">These mining models will allow you to explore the data using one model, and to create predictions using another.</span></span>  
  
 <span data-ttu-id="20760-105">Um herauszufinden, wie potenzielle Kunden anhand ihrer Merkmale kategorisiert werden können, erstellen Sie ein Mining Modell, das auf dem [Microsoft Clustering-Algorithmus](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md)basiert.</span><span class="sxs-lookup"><span data-stu-id="20760-105">To explore how potential customers can be categorized by their characteristics, you will create a mining model based on the [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span></span> <span data-ttu-id="20760-106">In einer späteren Lektion prüfen Sie, wie dieser Algorithmus Cluster von Kunden mit ähnlichen Merkmalen ermittelt.</span><span class="sxs-lookup"><span data-stu-id="20760-106">In a later lesson, you will explore how this algorithm finds clusters of customers who share similar characteristics.</span></span> <span data-ttu-id="20760-107">So könnten Sie beispielsweise ermitteln, dass bestimmte Kunden nicht weit voneinander entfernt leben, mit dem Fahrrad zur Arbeit fahren und über einen ähnlichen Bildungsstand verfügen.</span><span class="sxs-lookup"><span data-stu-id="20760-107">For example, you might find that certain customers tend to live close to each other, commute by bicycle, and have similar education backgrounds.</span></span> <span data-ttu-id="20760-108">Sie können diese Cluster dazu verwenden, das Beziehungsgefüge zwischen unterschiedlichen Kunden besser zu verstehen. Mithilfe der gewonnenen Informationen können Sie dann eine Marketingstrategie erstellen, die auf bestimmte Kunden abzielt.</span><span class="sxs-lookup"><span data-stu-id="20760-108">You can use these clusters to better understand how different customers are related, and to use the information to create a marketing strategy that targets specific customers.</span></span>  
  
 <span data-ttu-id="20760-109">Um vorherzusagen, ob ein potenzieller Kunde wahrscheinlich ein Fahrrad kaufen wird, erstellen Sie ein Mining Modell, das auf dem [Microsoft Decision Trees-Algorithmus](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md)basiert.</span><span class="sxs-lookup"><span data-stu-id="20760-109">To predict whether a potential customer is likely to buy a bicycle, you will create a mining model based on the [Microsoft Decision Trees Algorithm](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span></span> <span data-ttu-id="20760-110">Dieser Algorithmus analysiert die mit allen potenziellen Kunden verknüpften Informationen und sucht Merkmale, die für die Vorhersage, ob diese Kunden ein Fahrrad kaufen werden, hilfreich sein können.</span><span class="sxs-lookup"><span data-stu-id="20760-110">This algorithm looks through the information that is associated with each potential customer, and finds characteristics that are useful in predicting if they will buy a bicycle.</span></span> <span data-ttu-id="20760-111">Anschließend vergleicht der Algorithmus die Merkmale von Kunden, die in der Vergangenheit ein Fahrrad gekauft haben, mit den Merkmalen potenzieller Neukunden, um zu bestimmen, wie wahrscheinlich es ist, dass diese potenziellen Neukunden ein Fahrrad kaufen werden.</span><span class="sxs-lookup"><span data-stu-id="20760-111">It then compares the values of the characteristics of previous bike buyers against new potential customers to determine whether the new potential customers are likely to buy a bicycle.</span></span>  
  
## <a name="alter-mining-structure-statement"></a><span data-ttu-id="20760-112">ALTER MINING STRUCTURE-Anweisung</span><span class="sxs-lookup"><span data-stu-id="20760-112">ALTER MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="20760-113">Um der Mining Struktur ein Mining Modell hinzuzufügen, verwenden Sie die Anweisung [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) .</span><span class="sxs-lookup"><span data-stu-id="20760-113">In order to add a mining model to the mining structure, you use the [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) statement.</span></span> <span data-ttu-id="20760-114">Der in der Anweisung enthaltene Code umfasst folgende Abschnitte: </span><span class="sxs-lookup"><span data-stu-id="20760-114">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="20760-115">Identifizieren der Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="20760-115">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="20760-116">Benennen des Miningmodells</span><span class="sxs-lookup"><span data-stu-id="20760-116">Naming the mining model</span></span>  
  
-   <span data-ttu-id="20760-117">Definieren der Schlüsselspalte</span><span class="sxs-lookup"><span data-stu-id="20760-117">Defining the key column</span></span>  
  
-   <span data-ttu-id="20760-118">Definieren der Eingabespalten und vorhersagbaren Spalten</span><span class="sxs-lookup"><span data-stu-id="20760-118">Defining the input and predictable columns</span></span>  
  
-   <span data-ttu-id="20760-119">Identifizieren der Algorithmus- und Parameteränderungen</span><span class="sxs-lookup"><span data-stu-id="20760-119">Identifying the algorithm and parameter changes</span></span>  
  
 <span data-ttu-id="20760-120">Es folgt ein allgemeines Beispiel für die ALTER MINING MODEL-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="20760-120">The following is a generic example of the ALTER MINING MODEL statement:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
ADD MINING MODEL [<mining model name>]  
(  
    [<key column>],  
    <mining model columns>,  
) USING <algorithm name>( <algorithm parameters> )  
WITH FILTER (<expression>)  
```  
  
 <span data-ttu-id="20760-121">Die erste Codezeile identifiziert die vorhandene Miningstruktur, der die Miningmodelle hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="20760-121">The first line of the code identifies the existing mining structure to which the mining models will be added:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="20760-122">Die nächste Codezeile benennt das Miningmodell, das zur Miningstruktur hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="20760-122">The next line of the code names the mining model that will be added to the mining structure:</span></span>  
  
```  
ADD MINING MODEL [<mining model name>]  
```  
  
 <span data-ttu-id="20760-123">Weitere Informationen zum Benennen eines Objekts in DMX finden Sie unter Bezeichner [&#40;DMX-&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="20760-123">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="20760-124">Die nächsten Codezeilen definieren Spalten der Miningstruktur, die vom Miningmodell verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="20760-124">The next lines of the code define columns from the mining structure that will be used by the mining model:</span></span>  
  
```  
[<key column>],  
<mining model columns>  
```  
  
 <span data-ttu-id="20760-125">Sie können nur Spalten verwenden, die bereits in der Miningstruktur vorhanden sind; außerdem muss die erste Spalte in der Liste die Schlüsselspalte der Miningstruktur sein.</span><span class="sxs-lookup"><span data-stu-id="20760-125">You can only use columns that already exist in the mining structure, and the first column in the list must be the key column from the mining structure.</span></span>  
  
 <span data-ttu-id="20760-126">Die nächste Codezeile definiert den Miningalgorithmus, der das Miningmodell generiert, und die Algorithmusparameter, die Sie für den Algorithmus festlegen können:</span><span class="sxs-lookup"><span data-stu-id="20760-126">The next line of the code defines the mining algorithm that generates the mining model and the algorithm parameters that you can set on the algorithm:</span></span>  
  
```  
) USING <algorithm name>( <algorithm parameters> )  
```  
  
 <span data-ttu-id="20760-127">Weitere Informationen zu den Algorithmusparametern, die Sie anpassen können, finden Sie unter [Microsoft Decision Trees-Algorithmus](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md) und [Microsoft Clustering-Algorithmus](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="20760-127">For more information about the algorithm parameters that you can adjust, see [Microsoft Decision Trees Algorithm](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md) and [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md).</span></span>  
  
 <span data-ttu-id="20760-128">Mithilfe der folgenden Syntax können Sie angeben, dass eine Spalte des Miningmodells für Vorhersagen verwendet werden soll:</span><span class="sxs-lookup"><span data-stu-id="20760-128">You can specify that a column in the mining model be used for prediction by using the following syntax:</span></span>  
  
```  
<mining model column> PREDICT  
```  
  
 <span data-ttu-id="20760-129">Die letzte Codezeile ist optional und definiert einen Filter, der zum Trainieren und Testen des Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="20760-129">The final line of the code, which is optional, defines a filter that is applied when training and testing the model.</span></span> <span data-ttu-id="20760-130">Weitere Informationen zum Anwenden von Filtern auf Mining Modelle finden Sie unter [Filter für Mining Modelle &#40;Analysis Services Data Mining-&#41;](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="20760-130">For more information about how to apply filters to mining models, see [Filters for Mining Models &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="20760-131">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="20760-131">Lesson Tasks</span></span>  
 <span data-ttu-id="20760-132">Im Rahmen dieser Lektion führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="20760-132">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="20760-133">Hinzufügen eines Entscheidungsstruktur-Miningmodells zur Bike Buyer-Struktur mithilfe des [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="20760-133">Add a decision tree mining model to the Bike Buyer structure by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm</span></span>  
  
-   <span data-ttu-id="20760-134">Hinzufügen eines Clustering-Miningmodells zur Bike Buyer-Struktur mithilfe des [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="20760-134">Add a clustering mining model to the Bike Buyer structure by using the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm</span></span>  
  
-   <span data-ttu-id="20760-135">Da Sie Ergebnisse für alle Fälle anzeigen möchten, fügen Sie noch keinen Filter zu einem Modell hinzu.</span><span class="sxs-lookup"><span data-stu-id="20760-135">Because you want to see results for all cases, you will not yet add a filter to either model.</span></span>  
  
## <a name="adding-a-decision-tree-mining-model-to-the-structure"></a><span data-ttu-id="20760-136">Hinzufügen eines Entscheidungsstruktur-Miningmodells zur Struktur</span><span class="sxs-lookup"><span data-stu-id="20760-136">Adding a Decision Tree Mining Model to the Structure</span></span>  
 <span data-ttu-id="20760-137">Im ersten Schritt müssen Sie ein Miningmodell auf der Basis des [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees-Algorithmus hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="20760-137">The first step is to add a mining model based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Decision Trees algorithm.</span></span>  
  
#### <a name="to-add-a-decision-tree-mining-model"></a><span data-ttu-id="20760-138">So fügen Sie ein Entscheidungsstruktur-Miningmodell hinzu</span><span class="sxs-lookup"><span data-stu-id="20760-138">To add a decision tree mining model</span></span>  
  
1.  <span data-ttu-id="20760-139">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX** , um den Abfrage-Editor und eine neue, leere Abfrage zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="20760-139">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open Query Editor and a new, blank query.</span></span>  
  
2.  <span data-ttu-id="20760-140">Kopieren Sie das allgemeine Beispiel der ALTER MINING STRUCTURE-Anweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="20760-140">Copy the generic example of the ALTER MINING STRUCTURE statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="20760-141">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="20760-141">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="20760-142">durch:</span><span class="sxs-lookup"><span data-stu-id="20760-142">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  <span data-ttu-id="20760-143">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="20760-143">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="20760-144">durch:</span><span class="sxs-lookup"><span data-stu-id="20760-144">with:</span></span>  
  
    ```  
    Decision Tree  
    ```  
  
5.  <span data-ttu-id="20760-145">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="20760-145">Replace the following:</span></span>  
  
    ```  
    <mining model columns>,  
    ```  
  
     <span data-ttu-id="20760-146">durch:</span><span class="sxs-lookup"><span data-stu-id="20760-146">with:</span></span>  
  
    ```  
    (  
       CustomerKey,  
       [Age],  
       [Bike Buyer] PREDICT,  
       [Commute Distance],  
       [Education],  
       [Gender],  
       [House Owner Flag],  
       [Marital Status],  
       [Number Cars Owned],  
       [Number Children At Home],  
       [Occupation],  
       [Region],  
       [Total Children],  
       [Yearly Income]  
    ```  
  
     <span data-ttu-id="20760-147">In diesem Fall wurde die `[Bike Buyer]`-Spalte als die PREDICT-Spalte angegeben.</span><span class="sxs-lookup"><span data-stu-id="20760-147">In this case, the `[Bike Buyer]` column has been designated as the PREDICT column.</span></span>  
  
6.  <span data-ttu-id="20760-148">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="20760-148">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>( <algorithm parameters> )   
    ```  
  
     <span data-ttu-id="20760-149">durch:</span><span class="sxs-lookup"><span data-stu-id="20760-149">with:</span></span>  
  
    ```  
    Using Microsoft_Decision_Trees  
    WITH DRILLTHROUGH  
    ```  
  
     <span data-ttu-id="20760-150">Mithilfe der WITH DRILLTHROUGH-Anweisung können Sie die Fälle auswerten, die zum Erstellen des Miningmodells verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="20760-150">The WITH DRILLTHROUGH statement allows you to explore the cases that were used to build the mining model.</span></span>  
  
     <span data-ttu-id="20760-151">Die resultierende Anweisung sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="20760-151">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Bike Buyer]  
    ADD MINING MODEL [Decision Tree]  
    (  
       CustomerKey,  
       [Age],  
       [Bike Buyer] PREDICT,  
       [Commute Distance],  
       [Education],  
       [Gender],  
       [House Owner Flag],  
       [Marital Status],  
       [Number Cars Owned],  
       [Number Children At Home],  
       [Occupation],  
       [Region],  
       [Total Children],  
       [Yearly Income]  
    ) USING Microsoft_Decision_Trees  
    WITH DRILLTHROUGH  
    ```  
  
7.  <span data-ttu-id="20760-152">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="20760-152">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="20760-153">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `DT_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="20760-153">In the **Save As** dialog box, browse to the appropriate folder, and name the file `DT_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="20760-154">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="20760-154">On the toolbar, click the **Execute** button.</span></span>  
  
## <a name="adding-a-clustering-mining-model-to-the-structure"></a><span data-ttu-id="20760-155">Hinzufügen eines Clustering-Miningmodells zur Struktur</span><span class="sxs-lookup"><span data-stu-id="20760-155">Adding a Clustering Mining Model to the Structure</span></span>  
 <span data-ttu-id="20760-156">Sie können nun der Bike Buyer-Struktur ein Miningmodell hinzufügen, das auf dem [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering-Algorithmus basiert.</span><span class="sxs-lookup"><span data-stu-id="20760-156">You can now add a mining model to the Bike Buyer mining structure based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Clustering algorithm.</span></span> <span data-ttu-id="20760-157">Da das Clustering-Miningmodell alle Spalten verwendet, die in der Miningstruktur definiert sind, können Sie der Struktur das Modell vereinfacht hinzufügen, indem Sie darauf verzichten, die Miningspalten zu definieren.</span><span class="sxs-lookup"><span data-stu-id="20760-157">Because the clustering mining model will use all the columns defined in the mining structure, you can use a shortcut to add the model to the structure by omitting the definition of the mining columns.</span></span>  
  
#### <a name="to-add-a-clustering-mining-model"></a><span data-ttu-id="20760-158">So fügen Sie ein Clustering-Miningmodell hinzu</span><span class="sxs-lookup"><span data-stu-id="20760-158">To add a Clustering mining model</span></span>  
  
1.  <span data-ttu-id="20760-159">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX** , um den Abfrage-Editor zu öffnen und eine neue, leere Abfrage zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="20760-159">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open Query Editor opens and a new, blank query.</span></span>  
  
2.  <span data-ttu-id="20760-160">Kopieren Sie das allgemeine Beispiel der ALTER MINING STRUCTURE-Anweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="20760-160">Copy the generic example of the ALTER MINING STRUCTURE statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="20760-161">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="20760-161">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="20760-162">durch:</span><span class="sxs-lookup"><span data-stu-id="20760-162">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
4.  <span data-ttu-id="20760-163">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="20760-163">Replace the following:</span></span>  
  
    ```  
    <mining model>   
    ```  
  
     <span data-ttu-id="20760-164">durch:</span><span class="sxs-lookup"><span data-stu-id="20760-164">with:</span></span>  
  
    ```  
    Clustering Model  
    ```  
  
5.  <span data-ttu-id="20760-165">Löschen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="20760-165">Delete the following:</span></span>  
  
    ```  
    (  
        [<key column>],  
        <mining model columns>,  
    )  
    ```  
  
6.  <span data-ttu-id="20760-166">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="20760-166">Replace the following:</span></span>  
  
    ```  
    USING <algorithm name>( <algorithm parameters> )  
    ```  
  
     <span data-ttu-id="20760-167">durch:</span><span class="sxs-lookup"><span data-stu-id="20760-167">with:</span></span>  
  
    ```  
    USING Microsoft_Clustering  
    ```  
  
     <span data-ttu-id="20760-168">Die gesamte Anweisung sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="20760-168">The complete statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Bike Buyer]  
    ADD MINING MODEL [Clustering]  
    USING Microsoft_Clustering   
    ```  
  
7.  <span data-ttu-id="20760-169">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="20760-169">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="20760-170">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `Clustering_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="20760-170">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Clustering_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="20760-171">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="20760-171">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="20760-172">In der nächsten Lektion verarbeiten Sie die Modelle und die Miningstruktur.</span><span class="sxs-lookup"><span data-stu-id="20760-172">In the next lesson, you will process the models and the mining structure.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="20760-173">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="20760-173">Next Lesson</span></span>  
 [<span data-ttu-id="20760-174">Lektion 3: Verarbeiten der Bike Buyer-Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="20760-174">Lesson 3: Processing the Bike Buyer Mining Structure</span></span>](../../2014/tutorials/lesson-3-processing-the-bike-buyer-mining-structure.md)  
  
  
