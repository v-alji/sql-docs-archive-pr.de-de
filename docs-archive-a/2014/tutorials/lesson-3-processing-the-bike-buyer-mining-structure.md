---
title: 'Lektion 3: Verarbeiten der Bike Buyer-Mining Struktur | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e748c2cd-339d-4e82-82f1-be2d0fc41b61
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 2e3f85016b32884b9a6b809e28d20d9985f97cd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719078"
---
# <a name="lesson-3-processing-the-bike-buyer-mining-structure"></a><span data-ttu-id="1c7be-102">Lektion 3: Verarbeiten der Bike Buyer-Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="1c7be-102">Lesson 3: Processing the Bike Buyer Mining Structure</span></span>
  <span data-ttu-id="1c7be-103">In dieser Lektion verwenden Sie die INSERT INTO-Anweisung und die vTargetMail-Sicht aus der- [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] Beispieldatenbank, um die Mining Strukturen und Mining Modelle zu verarbeiten, die Sie in [Lektion 1: Erstellen der Bike Buyer-Mining Struktur](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md) und [Lektion 2: Hinzufügen von Mining Modellen zur Bike Buyer-Mining Struktur](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md)erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="1c7be-103">In this lesson, you will use the INSERT INTO statement and the vTargetMail view from the [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] sample database to process the mining structures and mining models that you created in [Lesson 1: Creating the Bike Buyer Mining Structure](../../2014/tutorials/lesson-1-creating-the-bike-buyer-mining-structure.md) and [Lesson 2: Adding Mining Models to the Bike Buyer Mining Structure](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md).</span></span>  
  
 <span data-ttu-id="1c7be-104">Wenn Sie eine Miningstruktur verarbeiten, liest [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] die Quelldaten und erstellt die Strukturen, die Miningmodelle unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1c7be-104">When you process a mining structure, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] reads the source data and builds the structures that support mining models.</span></span> <span data-ttu-id="1c7be-105">Wenn Sie ein Miningmodell verarbeiten, werden die von der Miningstruktur definierten Daten über den von Ihnen ausgewählten Data Mining-Algorithmus übergeben.</span><span class="sxs-lookup"><span data-stu-id="1c7be-105">When you process a mining model, the data defined by the mining structure is passed through the data mining algorithm that you choose.</span></span> <span data-ttu-id="1c7be-106">Der Algorithmus sucht nach Trends und Mustern und speichert diese Informationen dann im Miningmodell.</span><span class="sxs-lookup"><span data-stu-id="1c7be-106">The algorithm searches for trends and patterns, and then stores this information in the mining model.</span></span> <span data-ttu-id="1c7be-107">Aus diesem Grund enthält das Miningmodell nicht die tatsächlichen Quelldaten, sondern die vom Algorithmus ermittelten Informationen.</span><span class="sxs-lookup"><span data-stu-id="1c7be-107">The mining model, therefore, does not contain the actual source data, but instead contains the information that was discovered by the algorithm.</span></span> <span data-ttu-id="1c7be-108">Weitere Informationen zum Verarbeiten von Mining Modellen finden Sie unter [Verarbeiten von Anforderungen und Überlegungen &#40;Data Mining-&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="1c7be-108">For more information about processing mining models, see [Processing Requirements and Considerations &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/processing-requirements-and-considerations-data-mining.md).</span></span>  
  
 <span data-ttu-id="1c7be-109">Sie müssen eine Miningstruktur nur dann erneut verarbeiten, wenn Sie eine Strukturspalte oder die Quelldaten ändern.</span><span class="sxs-lookup"><span data-stu-id="1c7be-109">You need to reprocess a mining structure only if you change a structure column or change the source data.</span></span> <span data-ttu-id="1c7be-110">Wenn Sie einer Miningstruktur, die bereits verarbeitet wurde, ein Miningmodell hinzufügen, können Sie das neue Miningmodell mithilfe der INSERT INTO MINING MODEL-Anweisung trainieren.</span><span class="sxs-lookup"><span data-stu-id="1c7be-110">If you add a mining model to a mining structure that has already been processed, you can use the INSERT INTO MINING MODEL statement to train the new mining model.</span></span>  
  
## <a name="train-structure-template"></a><span data-ttu-id="1c7be-111">Trainieren der Strukturvorlage</span><span class="sxs-lookup"><span data-stu-id="1c7be-111">Train Structure Template</span></span>  
 <span data-ttu-id="1c7be-112">Um die Mining Struktur und die zugehörigen Mining Modelle zu trainieren, verwenden Sie die [INSERT INTO-Anweisung &#40;DMX-&#41;](/sql/dmx/insert-into-dmx) .</span><span class="sxs-lookup"><span data-stu-id="1c7be-112">In order to train the mining structure and its associated mining models, use the [INSERT INTO &#40;DMX&#41;](/sql/dmx/insert-into-dmx) statement.</span></span> <span data-ttu-id="1c7be-113">Der in der Anweisung enthaltene Code umfasst folgende Abschnitte: </span><span class="sxs-lookup"><span data-stu-id="1c7be-113">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="1c7be-114">Identifizieren der Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="1c7be-114">Identifying the mining structure</span></span>  
  
-   <span data-ttu-id="1c7be-115">Auflisten der Spalten in der Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="1c7be-115">Listing the columns in the mining structure</span></span>  
  
-   <span data-ttu-id="1c7be-116">Definieren der Trainingsdaten</span><span class="sxs-lookup"><span data-stu-id="1c7be-116">Defining the training data</span></span>  
  
 <span data-ttu-id="1c7be-117">Es folgt ein allgemeines Beispiel für die INSERT INTO-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="1c7be-117">The following is a generic example of the INSERT INTO statement:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
(  
   <mining structure columns>  
)  
OPENQUERY([<datasource>],'<SELECT statement>')  
```  
  
 <span data-ttu-id="1c7be-118">Die erste Codezeile identifiziert die Miningstruktur, die Sie trainieren werden:</span><span class="sxs-lookup"><span data-stu-id="1c7be-118">The first line of the code identifies the mining structure that you will train:</span></span>  
  
```  
INSERT INTO MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="1c7be-119">Die nächste Codezeile gibt die Spalten an, die durch die Miningstruktur definiert sind.</span><span class="sxs-lookup"><span data-stu-id="1c7be-119">The next line of the code specifies the columns that are defined by the mining structure.</span></span> <span data-ttu-id="1c7be-120">Sie müssen jede Spalte in der Miningstruktur auflisten, und jede Spalte muss einer in den Quellabfragedaten enthaltenen Spalte zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="1c7be-120">You must list each column in the mining structure, and each column must map to a column contained within the source query data.</span></span>  
  
```  
(  
   <mining structure columns>  
)  
```  
  
 <span data-ttu-id="1c7be-121">Die letzte Codezeile definiert die Daten, die zum Trainieren der Miningstruktur verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c7be-121">The final line of the code defines the data that will be used to train the mining structure:</span></span>  
  
```  
OPENQUERY([<datasource>],'<SELECT statement>')  
```  
  
 <span data-ttu-id="1c7be-122">In dieser Lektion verwenden Sie `OPENQUERY` zum Definieren der Quelldaten.</span><span class="sxs-lookup"><span data-stu-id="1c7be-122">In this lesson, you use `OPENQUERY` to define the source data.</span></span> <span data-ttu-id="1c7be-123">Weitere Informationen zu anderen Methoden zum Definieren der Quell Abfrage finden Sie unter [&#60;Quelldaten Abfrage&#62;](/sql/dmx/source-data-query).</span><span class="sxs-lookup"><span data-stu-id="1c7be-123">For information about other methods of defining the source query, see [&#60;source data query&#62;](/sql/dmx/source-data-query).</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="1c7be-124">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="1c7be-124">Lesson Tasks</span></span>  
 <span data-ttu-id="1c7be-125">Im Rahmen dieser Lektion führen Sie die folgende Aufgabe aus:</span><span class="sxs-lookup"><span data-stu-id="1c7be-125">You will perform the following task in this lesson:</span></span>  
  
-   <span data-ttu-id="1c7be-126">Verarbeiten der Bike Buyer-Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="1c7be-126">Process the Bike Buyer mining structure</span></span>  
  
## <a name="processing-the-predictive-mining-structure"></a><span data-ttu-id="1c7be-127">Verarbeiten der Vorhersageminingstruktur</span><span class="sxs-lookup"><span data-stu-id="1c7be-127">Processing the Predictive Mining Structure</span></span>  
  
#### <a name="to-process-the-mining-structure-by-using-insert-into"></a><span data-ttu-id="1c7be-128">So verarbeiten Sie die Miningstruktur mithilfe von INSERT INTO</span><span class="sxs-lookup"><span data-stu-id="1c7be-128">To process the mining structure by using INSERT INTO</span></span>  
  
1.  <span data-ttu-id="1c7be-129">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX**.</span><span class="sxs-lookup"><span data-stu-id="1c7be-129">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="1c7be-130">Der Abfrage-Editor wird mit einer neuen leeren Abfrage geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1c7be-130">Query Editor opens and contains a new, blank query.</span></span>  
  
2.  <span data-ttu-id="1c7be-131">Kopieren Sie das Standardbeispiel der INSERT INTO-Anweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="1c7be-131">Copy the generic example of the INSERT INTO statement into the blank query.</span></span>  
  
3.  <span data-ttu-id="1c7be-132">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1c7be-132">Replace the following:</span></span>  
  
    ```  
    [<mining structure name>]   
    ```  
  
     <span data-ttu-id="1c7be-133">durch:</span><span class="sxs-lookup"><span data-stu-id="1c7be-133">with:</span></span>  
  
    ```  
    Bike Buyer  
    ```  
  
4.  <span data-ttu-id="1c7be-134">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1c7be-134">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>  
    ```  
  
     <span data-ttu-id="1c7be-135">durch:</span><span class="sxs-lookup"><span data-stu-id="1c7be-135">with:</span></span>  
  
    ```  
    [Customer Key],  
    [Age],  
    [Bike Buyer],  
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
  
5.  <span data-ttu-id="1c7be-136">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1c7be-136">Replace the following:</span></span>  
  
    ```  
    OPENQUERY([<datasource>],'<SELECT statement>')  
    ```  
  
     <span data-ttu-id="1c7be-137">durch:</span><span class="sxs-lookup"><span data-stu-id="1c7be-137">with:</span></span>  
  
    ```  
    OPENQUERY([Adventure Works DW],  
       'SELECT CustomerKey, Age, BikeBuyer,  
             CommuteDistance,EnglishEducation,  
             Gender,HouseOwnerFlag,MaritalStatus,  
             NumberCarsOwned,NumberChildrenAtHome,   
             EnglishOccupation,Region,TotalChildren,  
             YearlyIncome   
        FROM dbo.vTargetMail')  
    ```  
  
     <span data-ttu-id="1c7be-138">Die OPENQUERY-Anweisung verweist auf die [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)]-Datenquelle, um auf die vTargetMail-Sicht zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="1c7be-138">The OPENQUERY statement references the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] data source to access the view vTargetMail.</span></span> <span data-ttu-id="1c7be-139">Die Sicht enthält die Quelldaten, die zum Trainieren der Miningmodelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1c7be-139">The view contains the source data that will be used to train the mining models.</span></span>  
  
     <span data-ttu-id="1c7be-140">Die gesamte Anweisung sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="1c7be-140">The complete statement should now be as follows:</span></span>  
  
    ```  
    INSERT INTO MINING STRUCTURE [Bike Buyer]  
    (  
       [Customer Key],  
       [Age],  
       [Bike Buyer],  
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
    )  
    OPENQUERY([Adventure Works DW],  
       'SELECT CustomerKey, Age, BikeBuyer,  
             CommuteDistance,EnglishEducation,  
             Gender,HouseOwnerFlag,MaritalStatus,  
             NumberCarsOwned,NumberChildrenAtHome,   
             EnglishOccupation,Region,TotalChildren,  
             YearlyIncome   
        FROM dbo.vTargetMail')  
    ```  
  
6.  <span data-ttu-id="1c7be-141">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="1c7be-141">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="1c7be-142">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `Process Bike Buyer Structure.dmx` .</span><span class="sxs-lookup"><span data-stu-id="1c7be-142">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Process Bike Buyer Structure.dmx`.</span></span>  
  
8.  <span data-ttu-id="1c7be-143">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="1c7be-143">On the toolbar, click the **Execute** button.</span></span>  
  
 <span data-ttu-id="1c7be-144">In der nächsten Lektion untersuchen Sie Miningmodellinhalte, die Sie der Miningstruktur in dieser Lektion hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="1c7be-144">In the next lesson, you will explore content in the mining models you added to the mining structure in this lesson.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="1c7be-145">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="1c7be-145">Next Lesson</span></span>  
 [<span data-ttu-id="1c7be-146">Lektion 4: Durchsuchen des Bike Buyer-Miningmodells</span><span class="sxs-lookup"><span data-stu-id="1c7be-146">Lesson 4: Browsing the Bike Buyer Mining Models</span></span>](../../2014/tutorials/lesson-4-browsing-the-bike-buyer-mining-models.md)  
  
  
