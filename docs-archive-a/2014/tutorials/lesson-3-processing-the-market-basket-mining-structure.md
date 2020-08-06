---
title: 'Lektion 3: Verarbeiten der Market Basket-Mining Struktur | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 095a043f-cf6f-45bb-a021-ae4e1b535c65
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: ce2c2e6944d524a38edc331d2cd128ca7cf7d419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694878"
---
# <a name="lesson-3-processing-the-market-basket-mining-structure"></a><span data-ttu-id="001b8-102">Lektion 3: Verarbeiten der Market Basket-Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="001b8-102">Lesson 3: Processing the Market Basket Mining Structure</span></span>
  <span data-ttu-id="001b8-103">In dieser Lektion verwenden Sie die [INSERT INTO-Anweisung &#40;DMX-&#41;](/sql/dmx/insert-into-dmx) und die vassoccot qlineitems und vAssoc/qorders aus der- [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] Beispieldatenbank, um die Mining Strukturen und Mining Modelle zu verarbeiten, die Sie in [Lektion 1: Erstellen der Market Basket-Mining Struktur](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md) und [Lektion 2: Hinzufügen von Mining Modellen zur Market Basket-Mining Struktur](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md)erstellen</span><span class="sxs-lookup"><span data-stu-id="001b8-103">In this lesson, you will use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement and the vAssocSeqLineItems and vAssocSeqOrders from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample database to process the mining structures and mining models that you created in [Lesson 1: Creating the Market Basket Mining Structure](../../2014/tutorials/lesson-1-creating-the-market-basket-mining-structure.md) and [Lesson 2: Adding Mining Models to the Market Basket Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md).</span></span>  
  
 <span data-ttu-id="001b8-104">Wenn Sie eine Miningstruktur verarbeiten, liest [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] die Quelldaten und erstellt die Strukturen, die Miningmodelle unterstützen.</span><span class="sxs-lookup"><span data-stu-id="001b8-104">When you process a mining structure, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] reads the source data and builds the structures that support mining models.</span></span> <span data-ttu-id="001b8-105">Wenn Sie ein Mining Modell verarbeiten, werden die Daten, die von der Mining Struktur definiert werden, über den Data Mining Algorithmus, den Sie ausgewählt haben, übermittelt.</span><span class="sxs-lookup"><span data-stu-id="001b8-105">When you process a mining model, the data defined by the mining structure is passed through the data mining algorithm that you chose.</span></span> <span data-ttu-id="001b8-106">Der Algorithmus sucht nach Trends und Mustern und speichert diese Informationen dann im Miningmodell.</span><span class="sxs-lookup"><span data-stu-id="001b8-106">The algorithm searches for trends and patterns, and then stores this information in the mining model.</span></span> <span data-ttu-id="001b8-107">Aus diesem Grund enthält das Miningmodell nicht die tatsächlichen Quelldaten, sondern die vom Algorithmus ermittelten Informationen.</span><span class="sxs-lookup"><span data-stu-id="001b8-107">The mining model, therefore, does not contain the actual source data, but instead contains the information that was discovered by the algorithm.</span></span> <span data-ttu-id="001b8-108">Weitere Informationen zum Verarbeiten von Mining Modellen finden Sie unter [Verarbeiten von Anforderungen und Überlegungen &#40;Data Mining-&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="001b8-108">For more information about processing mining models, see [Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span></span>  
  
 <span data-ttu-id="001b8-109">Sie müssen eine Miningstruktur nur erneut verarbeiten, wenn Sie eine Strukturspalte oder die Quelldaten ändern.</span><span class="sxs-lookup"><span data-stu-id="001b8-109">You only have to reprocess a mining structure if you change a structure column or change the source data.</span></span> <span data-ttu-id="001b8-110">Wenn Sie einer Miningstruktur, die bereits verarbeitet wurde, ein Miningmodell hinzufügen, können Sie das neue Miningmodell mithilfe der `INSERT INTO MINING MODEL`-Anweisung für die vorhandenen Daten trainieren.</span><span class="sxs-lookup"><span data-stu-id="001b8-110">If you add a mining model to a mining structure that has already been processed, you can use the `INSERT INTO MINING MODEL` statement to train the new mining model on the existing data.</span></span>  
  
 <span data-ttu-id="001b8-111">Da die Market Basket-Miningstruktur eine geschachtelte Tabelle enthält, müssen Sie die zu trainierenden Miningspalten mithilfe der Struktur der geschachtelten Tabelle definieren und mithilfe des `SHAPE`-Befehls die Abfragen definieren, die die Trainingsdaten aus den Quelltabellen extrahieren.</span><span class="sxs-lookup"><span data-stu-id="001b8-111">Because the Market Basket mining structure contains a nested table, you will have to define the mining columns to be trained using the nested table structure, and use the `SHAPE` command to define the queries that pull the training data from the source tables.</span></span>  
  
## <a name="insert-into-statement"></a><span data-ttu-id="001b8-112">INSERT INTO-Anweisung</span><span class="sxs-lookup"><span data-stu-id="001b8-112">INSERT INTO Statement</span></span>  
 <span data-ttu-id="001b8-113">Um die Market Basket-Mining Struktur und die zugehörigen Mining Modelle zu trainieren, verwenden Sie die [INSERT INTO-Anweisung &#40;DMX-&#41;](/sql/dmx/insert-into-dmx) .</span><span class="sxs-lookup"><span data-stu-id="001b8-113">In order to train the Market Basket mining structure and its associated mining models, use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement.</span></span> <span data-ttu-id="001b8-114">Der in der Anweisung enthaltene Code umfasst folgende Abschnitte. </span><span class="sxs-lookup"><span data-stu-id="001b8-114">The code in the statement can be broken into the following parts.</span></span>  
  
-   <span data-ttu-id="001b8-115">Identifizieren der Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="001b8-115">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="001b8-116">Auflisten der Spalten in der Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="001b8-116">Listing the columns in the mining structure</span></span>  
  
-   <span data-ttu-id="001b8-117">Definieren der Trainingsdaten mithilfe von `SHAPE`</span><span class="sxs-lookup"><span data-stu-id="001b8-117">Defining the training data using `SHAPE`</span></span>  
  
 <span data-ttu-id="001b8-118">Das folgende Beispiel ist ein allgemeines Beispiel für die `INSERT INTO`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="001b8-118">The following is a generic example of the `INSERT INTO` statement:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
(  
   <mining structure columns>  
   [<nested table>]  
   ( SKIP, <skipped column> )  
)  
SHAPE {  
  OPENQUERY([<datasource>],'<SELECT statement>') }  
APPEND  
(   
  {OPENQUERY([<datasource>],'<nested SELECT statement>')  
}  
RELATE [<case key>] TO [<foreign key>]  
) AS [<nested table>]  
```  
  
 <span data-ttu-id="001b8-119">Die erste Codezeile identifiziert die Miningstruktur, die Sie trainieren werden:</span><span class="sxs-lookup"><span data-stu-id="001b8-119">The first line of the code identifies the mining structure that you will train:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="001b8-120">Die nächsten Codezeilen geben die Spalten an, die durch die Miningstruktur definiert werden.</span><span class="sxs-lookup"><span data-stu-id="001b8-120">The next lines of the code specify the columns that are defined by the mining structure.</span></span> <span data-ttu-id="001b8-121">Sie müssen jede Spalte in der Miningstruktur auflisten, und jede Spalte muss einer in den Quellabfragedaten enthaltenen Spalte zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="001b8-121">You must list each column in the mining structure, and each column must map to a column contained within the source query data.</span></span> <span data-ttu-id="001b8-122">Sie können `SKIP` verwenden, um Spalten zu ignorieren, die in den Quelldaten, jedoch nicht in der Miningstruktur vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="001b8-122">You can use `SKIP` to ignore columns that exist in the source data but do not exist in the mining structure.</span></span> <span data-ttu-id="001b8-123">Weitere Informationen zum Verwenden von finden Sie `SKIP` unter [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx).</span><span class="sxs-lookup"><span data-stu-id="001b8-123">For more information about how to use `SKIP`, see [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx).</span></span>  
  
```  
(  
   <mining structure columns>  
   [<nested table>]  
   ( SKIP, <skipped column> )  
)  
```  
  
 <span data-ttu-id="001b8-124">Die letzten Codezeilen definieren die Daten, die zum Trainieren der Miningstruktur verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="001b8-124">The final lines of the code define the data that will be used to train the mining structure.</span></span> <span data-ttu-id="001b8-125">Da die Quelldaten auf zwei Tabellen verteilt sind, verwenden Sie `SHAPE`, um die Tabellen miteinander in Beziehung zu setzen.</span><span class="sxs-lookup"><span data-stu-id="001b8-125">Because the source data is contained within two tables, you will use `SHAPE` to relate the tables.</span></span>  
  
```  
SHAPE {  
  OPENQUERY([<datasource>],'<SELECT statement>') }  
APPEND  
(   
  {OPENQUERY([<datasource>],''<nested SELECT statement>'')  
}  
RELATE [<case key>] TO [<foreign key>]  
) AS [<nested table>]  
```  
  
 <span data-ttu-id="001b8-126">In dieser Lektion verwenden Sie `OPENQUERY` zum Definieren der Quelldaten.</span><span class="sxs-lookup"><span data-stu-id="001b8-126">In this lesson, you use `OPENQUERY` to define the source data.</span></span> <span data-ttu-id="001b8-127">Weitere Informationen zu anderen Methoden zum Definieren einer Abfrage für die Quelldaten finden Sie unter [&#60;Quelldaten Abfrage&#62;](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="001b8-127">For information about other methods of defining a query on the source data, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="001b8-128">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="001b8-128">Lesson Tasks</span></span>  
 <span data-ttu-id="001b8-129">Im Rahmen dieser Lektion führen Sie die folgende Aufgabe aus:</span><span class="sxs-lookup"><span data-stu-id="001b8-129">You will perform the following task in this lesson:</span></span>  
  
-   <span data-ttu-id="001b8-130">Verarbeiten der Market Basket-Mining Struktur</span><span class="sxs-lookup"><span data-stu-id="001b8-130">Process the Market Basket mining structure</span></span>  
  
## <a name="processing-the-market-basket-mining-structure"></a><span data-ttu-id="001b8-131">Verarbeiten der Market Basket-Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="001b8-131">Processing the Market Basket Mining Structure</span></span>  
  
#### <a name="to-process-the-mining-structure-by-using-insert-into"></a><span data-ttu-id="001b8-132">So verarbeiten Sie die Miningstruktur mithilfe von INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="001b8-132">To process the mining structure by using INSERT INTO</span></span>  
  
1.  <span data-ttu-id="001b8-133">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX**.</span><span class="sxs-lookup"><span data-stu-id="001b8-133">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="001b8-134">Der Abfrage-Editor wird mit einer neuen leeren Abfrage geöffnet.</span><span class="sxs-lookup"><span data-stu-id="001b8-134">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="001b8-135">Kopieren Sie das Standardbeispiel der INSERT INTO-Anweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="001b8-135">Copy the generic example of the INSERT INTO statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="001b8-136">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="001b8-136">Replace the following:</span></span>  
  
    ```  
    [<mining structure>]  
    ```  
  
     <span data-ttu-id="001b8-137">durch:</span><span class="sxs-lookup"><span data-stu-id="001b8-137">with:</span></span>  
  
    ```  
    Market Basket  
    ```  
  
4.  <span data-ttu-id="001b8-138">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="001b8-138">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>  
    [<nested table>]  
    ( SKIP, <skipped column> )  
    ```  
  
     <span data-ttu-id="001b8-139">durch:</span><span class="sxs-lookup"><span data-stu-id="001b8-139">with:</span></span>  
  
    ```  
    [OrderNumber],  
    [Products]   
    (SKIP, [Model])  
    ```  
  
     <span data-ttu-id="001b8-140">In der Anweisung verweist `Products` auf die von der SHAPE-Anweisung definierte Products-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="001b8-140">In the statement, `Products` refers to the Products table defined by the SHAPE statement.</span></span> <span data-ttu-id="001b8-141">`SKIP` wird verwendet, um die Model-Spalte zu ignorieren, die in den Quelldaten als Schlüssel existiert, aber nicht von der Miningstruktur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="001b8-141">`SKIP` is used to ignore the Model column, which exists in the source data as a key, but is not used by the mining structure.</span></span>  
  
5.  <span data-ttu-id="001b8-142">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="001b8-142">Replace the following:</span></span>  
  
    ```  
    SHAPE {  
      OPENQUERY([<datasource>],'<SELECT statement>') }  
    APPEND  
    (   
      {OPENQUERY([<datasource>],'<nested SELECT statement>')  
    }  
    RELATE [<case key>] TO [<foreign key>]  
    ) AS [<nested table>]  
    ```  
  
     <span data-ttu-id="001b8-143">durch:</span><span class="sxs-lookup"><span data-stu-id="001b8-143">with:</span></span>  
  
    ```  
    SHAPE {  
      OPENQUERY([Adventure Works DW],'SELECT OrderNumber  
                FROM vAssocSeqOrders ORDER BY OrderNumber')}  
    APPEND  
    (   
      {OPENQUERY([Adventure Works DW],'SELECT OrderNumber, Model FROM   
        dbo.vAssocSeqLineItems ORDER BY OrderNumber, Model')  
    }  
    RELATE OrderNumber to OrderNumber   
    ) AS [Products]  
    ```  
  
     <span data-ttu-id="001b8-144">Die Quell Abfrage verweist [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] auf die im Beispiel Projekt definierte Datenquelle [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="001b8-144">The source query references the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] data source defined in the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample project.</span></span> <span data-ttu-id="001b8-145">Sie verwendet diese Datenquelle für den Zugriff auf die Sichten vAssocSeqLineItems und vAssocSeqOrders.</span><span class="sxs-lookup"><span data-stu-id="001b8-145">It uses this data source to access the vAssocSeqLineItems and vAssocSeqOrders views.</span></span> <span data-ttu-id="001b8-146">Diese Sichten enthalten die Quelldaten, die zum Trainieren des Miningmodells verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="001b8-146">These views contain the source data that will be used to train the mining model.</span></span> <span data-ttu-id="001b8-147">Wenn Sie dieses Projekt oder diese Sichten nicht erstellt haben, finden Sie weitere Informationen unter [Tutorial zu Data Mining-Grundlagen](../../2014/tutorials/basic-data-mining-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="001b8-147">If you have not created this project or these views, see [Basic Data Mining Tutorial](../../2014/tutorials/basic-data-mining-tutorial.md).</span></span>  
  
     <span data-ttu-id="001b8-148">Im `SHAPE`-Befehl verwenden Sie `OPENQUERY`, um zwei Abfragen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="001b8-148">Within the `SHAPE` command, you will use `OPENQUERY` to define two queries.</span></span> <span data-ttu-id="001b8-149">Die erste Abfrage definiert die übergeordnete Tabelle und die zweite Abfrage definiert die geschachtelte Tabelle.</span><span class="sxs-lookup"><span data-stu-id="001b8-149">The first query defines the parent table, and the second query defines the nested table.</span></span> <span data-ttu-id="001b8-150">Die zwei Tabellen werden mithilfe der OrderNumber-Spalte, die in beiden Tabellen vorhanden ist, miteinander in Beziehung gesetzt.</span><span class="sxs-lookup"><span data-stu-id="001b8-150">The two tables are related using the OrderNumber column, which exists in both tables.</span></span>  
  
     <span data-ttu-id="001b8-151">Die gesamte Anweisung sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="001b8-151">The complete statement should now be as follows:</span></span>  
  
    ```  
    INSERT INTO MINING STRUCTURE [Market Basket]  
    (  
       [OrderNumber],[Products] (SKIP, [Model])  
    )  
    SHAPE {  
      OPENQUERY([Adventure Works DW],'SELECT OrderNumber  
                FROM vAssocSeqOrders ORDER BY OrderNumber')}  
    APPEND  
    (   
      {OPENQUERY([Adventure Works DW],'SELECT OrderNumber, Model FROM   
        dbo.vAssocSeqLineItems ORDER BY OrderNumber, Model')  
    }  
    RELATE OrderNumber to OrderNumber   
    ) AS [Products]  
    ```  
  
6.  <span data-ttu-id="001b8-152">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="001b8-152">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="001b8-153">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `Process Market Basket.dmx` .</span><span class="sxs-lookup"><span data-stu-id="001b8-153">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Process Market Basket.dmx`.</span></span>  
  
8.  <span data-ttu-id="001b8-154">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="001b8-154">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="001b8-155">Nachdem die Abfrage ausgeführt wurde, werden die gefundenen Muster und Itemsets sowie die Zuordnungen angezeigt, außerdem können Sie nach Itemset, Wahrscheinlichkeit oder Wichtigkeit filtern.</span><span class="sxs-lookup"><span data-stu-id="001b8-155">After the query has finished running, you can view the patterns and itemsets that were found, view associations, or filter by itemset, probability, or importance.</span></span> <span data-ttu-id="001b8-156">Um diese Informationen anzuzeigen, klicken Sie in mit [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] der rechten Maustaste auf den Namen des Datenmodells, und klicken Sie dann auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="001b8-156">To view this information, in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click the name of the data model, and then click **Browse**.</span></span>  
  
 <span data-ttu-id="001b8-157">In der nächsten Lektion erstellen Sie mehrere Vorhersagen auf der Basis des Miningmodells, das Sie der Market Basket-Struktur hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="001b8-157">In the next lesson, you will create several predictions based on the mining models that you added to the Market Basket structure.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="001b8-158">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="001b8-158">Next Lesson</span></span>  
 [<span data-ttu-id="001b8-159">Lektion 4: Ausführen von Warenkorbvorhersagen</span><span class="sxs-lookup"><span data-stu-id="001b8-159">Lesson 4: Executing Market Basket Predictions</span></span>](../../2014/tutorials/lesson-4-executing-market-basket-predictions.md)  
  
  
