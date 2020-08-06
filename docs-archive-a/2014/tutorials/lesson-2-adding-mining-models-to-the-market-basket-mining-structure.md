---
title: 'Lektion 2: Hinzufügen von Mining Modellen zur Market Basket-Mining Struktur | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d96a7a7d-35d7-4b34-abb5-f0822c256253
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: b9573d9359983e33cf23533787c26039572710ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717098"
---
# <a name="lesson-2-adding-mining-models-to-the-market-basket-mining-structure"></a><span data-ttu-id="b80cc-102">Lektion 2: Hinzufügen von Miningmodellen zur Market Basket-Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="b80cc-102">Lesson 2: Adding Mining Models to the Market Basket Mining Structure</span></span>
  <span data-ttu-id="b80cc-103">In dieser Lektion fügen Sie der Market Basket-Mining Struktur zwei Mining Modelle hinzu, die Sie in [Lektion 1: Erstellen der Market Basket-Mining Struktur](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md)erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b80cc-103">In this lesson, you will add two mining models to the Market Basket mining structure that you created in [Lesson 1: Creating the Market Basket Mining Structure](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md).</span></span> <span data-ttu-id="b80cc-104">Diese Miningmodelle ermöglichen es Ihnen, Vorhersagen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b80cc-104">These mining models will allow you to create predictions.</span></span>  
  
 <span data-ttu-id="b80cc-105">Um die Produkttypen vorherzusagen, die Kunden tendenziell gleichzeitig kaufen, erstellen Sie zwei Mining Modelle mithilfe des [Microsoft Association-Algorithmus](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md) und zwei unterschiedliche Werte für den *MINIMUM_PROBABILTY* -Parameter.</span><span class="sxs-lookup"><span data-stu-id="b80cc-105">To predict the types of products that customers tend to purchase at the same time, you will create two mining models using the [Microsoft Association Algorithm](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md) and two different values for the *MINIMUM_PROBABILTY* parameter.</span></span>  
  
 <span data-ttu-id="b80cc-106">*MINIMUM_PROBABILTY* ist ein [!INCLUDE[msCoName](../includes/msconame-md.md)] Association-Algorithmusparameter, mit dem die Anzahl der Regeln bestimmt wird, die ein Mining Modell enthalten wird, indem die minimale Wahrscheinlichkeit angegeben wird, die eine Regel aufweisen muss.</span><span class="sxs-lookup"><span data-stu-id="b80cc-106">*MINIMUM_PROBABILTY* is a [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm parameter that helps to determine the number of rules that a mining model will contain by specifying the minimum probability that a rule must have.</span></span> <span data-ttu-id="b80cc-107">Wenn Sie für diesen Wert beispielsweise 0,4 eingeben, wird festgelegt, dass eine Regel nur erzeugt werden kann, wenn die Kombination der von der Regel beschriebenen Produkte eine Auftrittswahrscheinlichkeit von mindestens vierzig Prozent aufweist.</span><span class="sxs-lookup"><span data-stu-id="b80cc-107">For example, setting this value to 0.4 specifies that a rule can be generated only if the combination of products that the rule describes has at least a forty percent probability of occurring.</span></span>  
  
 <span data-ttu-id="b80cc-108">Sie werden die Auswirkung der Änderung des *MINIMUM_PROBABILTY* -Parameters in einer späteren Lektion anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b80cc-108">You will view the effect of changing the *MINIMUM_PROBABILTY* parameter in a later lesson.</span></span>  
  
## <a name="alter-mining-structure-statement"></a><span data-ttu-id="b80cc-109">ALTER MINING STRUCTURE-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b80cc-109">ALTER MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="b80cc-110">Wenn Sie ein Mining Modell, das eine Tabelle enthält, einer Mining Struktur hinzufügen möchten, verwenden Sie die Anweisung [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) .</span><span class="sxs-lookup"><span data-stu-id="b80cc-110">To add a mining model that contains a nested table to a mining structure, you use the [ALTER MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/alter-mining-structure-dmx?view=sql-server-2016) statement.</span></span> <span data-ttu-id="b80cc-111">Der in der Anweisung enthaltene Code umfasst folgende Abschnitte: </span><span class="sxs-lookup"><span data-stu-id="b80cc-111">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="b80cc-112">Identifizieren der Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="b80cc-112">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="b80cc-113">Benennen des Miningmodells</span><span class="sxs-lookup"><span data-stu-id="b80cc-113">Naming the mining model</span></span>  
  
-   <span data-ttu-id="b80cc-114">Definieren der Schlüsselspalte</span><span class="sxs-lookup"><span data-stu-id="b80cc-114">Defining the key column</span></span>  
  
-   <span data-ttu-id="b80cc-115">Definieren der Eingabespalten und vorhersagbaren Spalten</span><span class="sxs-lookup"><span data-stu-id="b80cc-115">Defining the input and predictable columns</span></span>  
  
-   <span data-ttu-id="b80cc-116">Definieren der Spalten der geschachtelten Tabellen</span><span class="sxs-lookup"><span data-stu-id="b80cc-116">Defining the nested table columns</span></span>  
  
-   <span data-ttu-id="b80cc-117">Identifizieren der Algorithmus- und Parameteränderungen</span><span class="sxs-lookup"><span data-stu-id="b80cc-117">Identifying the algorithm and parameter changes</span></span>  
  
 <span data-ttu-id="b80cc-118">Im Folgenden finden Sie ein allgemeines Beispiel der `ALTER MINING STRUCTURE`-Anweisung, das einer Struktur mit geschachtelten Tabellenspalten ein Miningmodell hinzufügt:</span><span class="sxs-lookup"><span data-stu-id="b80cc-118">The following is a generic example of the `ALTER MINING STRUCTURE` statement that adds a mining model to a structure that includes nested table columns:</span></span>  
  
```  
ALTER MINING STRUCTURE [<Mining Structure Name>]  
ADD MINING MODEL [<Mining Model Name>]  
(  
    [<key column>],  
    <mining model column> <usage>,  
    <table columns>  
    (  [<nested key column>],  
       <nested mining model columns> )  
) USING <algorithm>( <algorithm parameters> )  
```  
  
 <span data-ttu-id="b80cc-119">Die erste Codezeile identifiziert die vorhandene Miningstruktur, der das Miningmodell hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="b80cc-119">The first line of the code identifies the existing mining structure to which the mining model will be added:</span></span>  
  
```  
ALTER MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="b80cc-120">Die nächste Codezeile benennt das Miningmodell, das zur Miningstruktur hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="b80cc-120">The next line of the code names the mining model that will be added to the mining structure:</span></span>  
  
```  
ADD MINING MODEL [<mining model name>]  
```  
  
 <span data-ttu-id="b80cc-121">Weitere Informationen zum Benennen eines Objekts in Data Mining-Erweiterungen (DMX) finden Sie unter Bezeichner [&#40;DMX-&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="b80cc-121">For information about naming an object in Data Mining Extensions (DMX), see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="b80cc-122">Die nächsten Codezeilen definieren Spalten in der Miningstruktur, die vom Miningmodell verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="b80cc-122">The next lines of the code define the columns in the mining structure that will be used by the mining model:</span></span>  
  
```  
[<key column>],  
<mining model columns> <usage>,  
```  
  
 <span data-ttu-id="b80cc-123">Sie können nur Spalten verwenden, die bereits in der Miningstruktur vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b80cc-123">You can only use columns that already exist in the mining structure.</span></span>  
  
 <span data-ttu-id="b80cc-124">Die erste Spalte in der Liste der Miningmodellspalten muss die Schlüsselspalte in der Miningstruktur sein.</span><span class="sxs-lookup"><span data-stu-id="b80cc-124">The first column in the list of mining model columns must be the key column in the mining structure.</span></span> <span data-ttu-id="b80cc-125">Sie müssen jedoch nicht `KEY` nach der Schlüssel Spalte eingeben, um die Verwendung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b80cc-125">However, you do not have to type `KEY` after the key column to specify usage.</span></span> <span data-ttu-id="b80cc-126">Dies liegt daran, dass Sie die Spalte bereits bei der Erstellung der Miningstruktur als Schlüsselspalte definiert haben.</span><span class="sxs-lookup"><span data-stu-id="b80cc-126">That is because you have already defined the column as a key when you created the mining structure.</span></span>  
  
 <span data-ttu-id="b80cc-127">Die übrigen Zeilen geben die Verwendung der Spalten im neuen Miningmodell an.</span><span class="sxs-lookup"><span data-stu-id="b80cc-127">The remaining lines specify the usage of the columns in the new mining model.</span></span> <span data-ttu-id="b80cc-128">Mithilfe der folgenden Syntax können Sie angeben, dass eine Spalte im Miningmodell zur Vorhersage verwendet werden soll:</span><span class="sxs-lookup"><span data-stu-id="b80cc-128">You can specify that a column in the mining model will be used for prediction by using the following syntax:</span></span>  
  
```  
<column name> PREDICT,  
```  
  
 <span data-ttu-id="b80cc-129">Wenn Sie die Verwendung nicht festlegen, brauchen Sie der Liste keine Data Mining-Strukturspalte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b80cc-129">If you do not specify usage, you do not have to include a data mining structure column in the list.</span></span> <span data-ttu-id="b80cc-130">Alle Spalten, die von der Data Mining-Struktur verwendet werden, auf die verwiesen wird, stehen automatisch den Miningmodellen zur Verfügung, die auf dieser Struktur basieren.</span><span class="sxs-lookup"><span data-stu-id="b80cc-130">All columns that are used by the referenced data mining structure are automatically available for use by the mining models that are based on that structure.</span></span> <span data-ttu-id="b80cc-131">Das Modell verwendet die Spalten jedoch nicht für das Training, es sei den, Sie geben die Verwendung an.</span><span class="sxs-lookup"><span data-stu-id="b80cc-131">However, the model will not use the columns for training unless you specify the usage.</span></span>  
  
 <span data-ttu-id="b80cc-132">Die letzte Codezeile definiert den Algorithmus und die Algorithmusparameter, die zum Generieren des Miningmodells verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b80cc-132">The last line in the code defines the algorithm and algorithm parameters that will be used to generate the mining model.</span></span>  
  
```  
) USING <algorithm>( <algorithm parameters> )  
```  
  
## <a name="lesson-tasks"></a><span data-ttu-id="b80cc-133">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="b80cc-133">Lesson Tasks</span></span>  
 <span data-ttu-id="b80cc-134">Im Rahmen dieser Lektion führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="b80cc-134">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="b80cc-135">Hinzufügen eines Association-Miningmodells zur Struktur mithilfe der Standardwahrscheinlichkeit</span><span class="sxs-lookup"><span data-stu-id="b80cc-135">Add an association mining model to the structure using the default probability</span></span>  
  
-   <span data-ttu-id="b80cc-136">Hinzufügen eines Association-Miningmodells zur Struktur mithilfe einer geänderten Wahrscheinlichkeit</span><span class="sxs-lookup"><span data-stu-id="b80cc-136">Add an association mining model to the structure using a modified probability</span></span>  
  
## <a name="adding-an-association-mining-model-to-the-structure-using-the-default-minimum_probability"></a><span data-ttu-id="b80cc-137">Hinzufügen eines Association-Miningmodells zur Struktur mithilfe des MINIMUM_PROBABILITY-Standardwerts</span><span class="sxs-lookup"><span data-stu-id="b80cc-137">Adding an Association Mining Model to the Structure Using the Default MINIMUM_PROBABILITY</span></span>  
 <span data-ttu-id="b80cc-138">Die erste Aufgabe besteht darin, der Market Basket-Mining Struktur basierend auf dem Association-Algorithmus ein neues Mining Modell hinzuzufügen, [!INCLUDE[msCoName](../includes/msconame-md.md)] das den Standardwert für *MINIMUM_PROBABILITY*verwendet.</span><span class="sxs-lookup"><span data-stu-id="b80cc-138">The first task is to add a new mining model to the Market Basket mining structure based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm using the default value for *MINIMUM_PROBABILITY*.</span></span>  
  
#### <a name="to-add-an-association-mining-model"></a><span data-ttu-id="b80cc-139">So fügen Sie ein Association-Miningmodell hinzu</span><span class="sxs-lookup"><span data-stu-id="b80cc-139">To add an Association mining model</span></span>  
  
1.  <span data-ttu-id="b80cc-140">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX**.</span><span class="sxs-lookup"><span data-stu-id="b80cc-140">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="b80cc-141">Der Abfrage-Editor wird mit einer neuen leeren Abfrage geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b80cc-141">Query Editor opens and contains a new, blank query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b80cc-142">Um eine DMX-Abfrage für eine bestimmte [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Datenbank zu erstellen, klicken Sie mit der rechten Maustaste auf die Datenbank anstatt auf die Instanz.</span><span class="sxs-lookup"><span data-stu-id="b80cc-142">To create a DMX query against a specific [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, right-click the database instead of the instance.</span></span>  
  
2.  <span data-ttu-id="b80cc-143">Kopieren Sie das Standardbeispiel der `ALTER MINING STRUCTURE`-Anweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="b80cc-143">Copy the generic example of the `ALTER MINING STRUCTURE` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="b80cc-144">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b80cc-144">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="b80cc-145">durch:</span><span class="sxs-lookup"><span data-stu-id="b80cc-145">with:</span></span>  
  
    ```  
    [Market Basket]  
    ```  
  
4.  <span data-ttu-id="b80cc-146">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b80cc-146">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="b80cc-147">durch:</span><span class="sxs-lookup"><span data-stu-id="b80cc-147">with:</span></span>  
  
    ```  
    [Default Association]  
    ```  
  
5.  <span data-ttu-id="b80cc-148">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b80cc-148">Replace the following:</span></span>  
  
    ```  
    [<key column>],  
    <mining model columns>,  
    <table columns>  
    (  [<nested key column>],  
       <nested mining model columns> )  
    ```  
  
     <span data-ttu-id="b80cc-149">durch:</span><span class="sxs-lookup"><span data-stu-id="b80cc-149">with:</span></span>  
  
    ```  
    OrderNumber,  
        [Products] PREDICT (  
            [Model]  
        )  
    ```  
  
     <span data-ttu-id="b80cc-150">In diesem Fall wurde die Tabelle `[Products]` als vorhersagbare Spalte festgelegt`.` Außerdem wurde die Spalte `[Model]` in die Liste der geschachtelten Tabellenspalten eingefügt, da sie die Schlüsselspalte der geschachtelten Tabelle ist.</span><span class="sxs-lookup"><span data-stu-id="b80cc-150">In this case, the `[Products]` table has been designated as the predictable column`.` Also, the `[Model]` column is included in the list of nested table columns because it is the key column of the nested table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b80cc-151">Beachten Sie, dass sich ein geschachtelter Schlüssel von einem Fallschlüssel unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="b80cc-151">Remember that a nested key is different from a case key.</span></span> <span data-ttu-id="b80cc-152">Ein Fallschlüssel ist ein eindeutiger Bezeichner des Falles, während ein geschachtelter Schlüssel ein Attribut ist, dass Sie modellieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b80cc-152">A case key is a unique identifier of the case, whereas the nested key is an attribute that you want to model.</span></span>  
  
6.  <span data-ttu-id="b80cc-153">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b80cc-153">Replace the following:</span></span>  
  
    ```  
    USING <algorithm>( <algorithm parameters> )  
    ```  
  
     <span data-ttu-id="b80cc-154">durch:</span><span class="sxs-lookup"><span data-stu-id="b80cc-154">with:</span></span>  
  
    ```  
    Using Microsoft_Association_Rules  
    ```  
  
     <span data-ttu-id="b80cc-155">Die resultierende Anweisung sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="b80cc-155">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Market Basket]  
    ADD MINING MODEL [Default Association]  
    (  
        OrderNumber,  
        [Products] PREDICT (  
            [Model]  
        )  
    )  
    Using Microsoft_Association_Rules  
    ```  
  
7.  <span data-ttu-id="b80cc-156">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="b80cc-156">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="b80cc-157">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `Default_Association_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="b80cc-157">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Default_Association_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="b80cc-158">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="b80cc-158">On the toolbar, click the **Execute** button.</span></span>  
  
## <a name="adding-an-association-mining-model-to-the-structure-changing-the-default-minimum_probability"></a><span data-ttu-id="b80cc-159">Hinzufügen eines Association-Miningmodells zur Struktur, indem der Standardwert für MINIMUM_PROBABILITY geändert wurde</span><span class="sxs-lookup"><span data-stu-id="b80cc-159">Adding an Association Mining Model to the Structure Changing the Default MINIMUM_PROBABILITY</span></span>  
 <span data-ttu-id="b80cc-160">Im nächsten Schritt fügen Sie der Market Basket-Miningstruktur auf der Grundlage des [!INCLUDE[msCoName](../includes/msconame-md.md)] Association-Algorithmus ein neues Miningmodell hinzu und ändern den Standardwert für MINIMUM_PROBABILITY in 0,01.</span><span class="sxs-lookup"><span data-stu-id="b80cc-160">The next task is to add a new mining model to the Market Basket mining structure based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm, and change the default value for MINIMUM_PROBABILITY to 0.01.</span></span> <span data-ttu-id="b80cc-161">Das Ändern des Parameters bewirkt, dass der [!INCLUDE[msCoName](../includes/msconame-md.md)] Association-Algorithmus mehr Regeln erstellt.</span><span class="sxs-lookup"><span data-stu-id="b80cc-161">Changing the parameter will cause the [!INCLUDE[msCoName](../includes/msconame-md.md)] Association algorithm to create more rules.</span></span>  
  
#### <a name="to-add-an-association-mining-model"></a><span data-ttu-id="b80cc-162">So fügen Sie ein Association-Miningmodell hinzu</span><span class="sxs-lookup"><span data-stu-id="b80cc-162">To add an Association mining model</span></span>  
  
1.  <span data-ttu-id="b80cc-163">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX**.</span><span class="sxs-lookup"><span data-stu-id="b80cc-163">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="b80cc-164">Der Abfrage-Editor wird mit einer neuen leeren Abfrage geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b80cc-164">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="b80cc-165">Kopieren Sie das Standardbeispiel der `ALTER MINING STRUCTURE`-Anweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="b80cc-165">Copy the generic example of the `ALTER MINING STRUCTURE` statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="b80cc-166">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b80cc-166">Replace the following:</span></span>  
  
    ```  
    <mining structure name>   
    ```  
  
     <span data-ttu-id="b80cc-167">durch:</span><span class="sxs-lookup"><span data-stu-id="b80cc-167">with:</span></span>  
  
    ```  
    Market Basket  
    ```  
  
4.  <span data-ttu-id="b80cc-168">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b80cc-168">Replace the following:</span></span>  
  
    ```  
    <mining model name>   
    ```  
  
     <span data-ttu-id="b80cc-169">durch:</span><span class="sxs-lookup"><span data-stu-id="b80cc-169">with:</span></span>  
  
    ```  
    [Modified Association]  
    ```  
  
5.  <span data-ttu-id="b80cc-170">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b80cc-170">Replace the following:</span></span>  
  
    ```  
    <mining model columns>,  
    <table columns>  
    (  [<nested key column>],  
       <nested mining model columns> )  
    ```  
  
     <span data-ttu-id="b80cc-171">durch:</span><span class="sxs-lookup"><span data-stu-id="b80cc-171">with:</span></span>  
  
    ```  
    OrderNumber,  
    [Products] PREDICT (  
            [Model]  
        )  
    ```  
  
     <span data-ttu-id="b80cc-172">In diesem Fall wurde die Tabelle `[Products]` als vorhersagbare Spalte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b80cc-172">In this case, the `[Products]` table has been designated as the predictable column.</span></span> <span data-ttu-id="b80cc-173">Außerdem wurde der Liste die Spalte `[MODEL]` hinzugefügt, da sie in der geschachtelten Tabelle die Schlüsselspalte ist.</span><span class="sxs-lookup"><span data-stu-id="b80cc-173">Also, the `[MODEL]` column is included in the list because it is the key column in the nested table.</span></span>  
  
6.  <span data-ttu-id="b80cc-174">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b80cc-174">Replace the following:</span></span>  
  
    ```  
    USING <algorithm>( <algorithm parameters> )  
    ```  
  
     <span data-ttu-id="b80cc-175">durch:</span><span class="sxs-lookup"><span data-stu-id="b80cc-175">with:</span></span>  
  
    ```  
    USING Microsoft_Association_Rules (Minimum_Probability = 0.1)  
    ```  
  
     <span data-ttu-id="b80cc-176">Die resultierende Anweisung sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="b80cc-176">The resulting statement should now be as follows:</span></span>  
  
    ```  
    ALTER MINING STRUCTURE [Market Basket]  
    ADD MINING MODEL [Modified Assocation]  
    (  
        OrderNumber,  
        [Products] PREDICT (  
            [Model]  
        )  
    )  
    USING Microsoft_Association_Rules (Minimum_Probability = 0.1)  
    ```  
  
7.  <span data-ttu-id="b80cc-177">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="b80cc-177">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
8.  <span data-ttu-id="b80cc-178">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `Modified Association_Model.dmx` .</span><span class="sxs-lookup"><span data-stu-id="b80cc-178">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Modified Association_Model.dmx`.</span></span>  
  
9. <span data-ttu-id="b80cc-179">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="b80cc-179">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="b80cc-180">In der nächsten Lektion verarbeiten Sie die Market Basket-Miningstruktur zusammen mit den ihr zugeordneten Miningmodellen.</span><span class="sxs-lookup"><span data-stu-id="b80cc-180">In this next lesson you will process the Market Basket mining structure together with its associated mining models.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="b80cc-181">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="b80cc-181">Next Lesson</span></span>  
 [<span data-ttu-id="b80cc-182">Lektion 3: Verarbeiten der Market Basket-Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="b80cc-182">Lesson 3: Processing the Market Basket Mining Structure</span></span>](../../2014/tutorials/lesson-3-processing-the-market-basket-mining-structure.md)  
  
  
