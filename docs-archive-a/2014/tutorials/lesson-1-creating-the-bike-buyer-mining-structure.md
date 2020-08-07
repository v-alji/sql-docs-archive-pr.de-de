---
title: 'Lektion 1: Erstellen der Bike Buyer-Mining Struktur | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a73ac60b-660f-458a-bd2f-993fbeba7226
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: d6384910858d87a80aa3c8f897bc88e45f4504fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719096"
---
# <a name="lesson-1-creating-the-bike-buyer-mining-structure"></a><span data-ttu-id="309bf-102">Lektion 1: Erstellen der Bike Buyer-Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="309bf-102">Lesson 1: Creating the Bike Buyer Mining Structure</span></span>
  <span data-ttu-id="309bf-103">In dieser Lektion erstellen Sie eine Miningstruktur, mit der sich vorhersagen lässt, ob ein potenzieller Kunde von [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] ein Fahrrad kaufen wird.</span><span class="sxs-lookup"><span data-stu-id="309bf-103">In this lesson, you will create a mining structure that allows you to predict whether a potential customer of [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] will purchase a bicycle.</span></span> <span data-ttu-id="309bf-104">Wenn Sie mit Mining Strukturen und deren Rolle in Data Mining nicht vertraut sind, finden Sie weitere Informationen unter [Mining Strukturen &#40;Analysis Services Data Mining-&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="309bf-104">If you are unfamiliar with mining structures and their role in data mining, see [Mining Structures &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="309bf-105">Die Bike Buyer-Mining Struktur, die Sie in dieser Lektion erstellen, unterstützt das Hinzufügen von Mining Modellen, die [auf dem Microsoft](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md)[Decision Trees](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md)-Algorithmus basieren.</span><span class="sxs-lookup"><span data-stu-id="309bf-105">The Bike Buyer mining structure that you will create in this lesson supports adding mining models based on the [Microsoft Clustering Algorithm](../../2014/analysis-services/data-mining/microsoft-clustering-algorithm.md)[Microsoft Decision Trees Algorithm](../../2014/analysis-services/data-mining/microsoft-decision-trees-algorithm.md).</span></span> <span data-ttu-id="309bf-106">In späteren Lektionen untersuchen Sie mithilfe der Clustering-Miningmodelle verschiedene Möglichkeiten zum Gruppieren von Kunden und verwenden Entscheidungsstruktur-Miningmodelle, um vorherzusagen, ob ein potenzieller Kunde ein Fahrrad kaufen wird oder nicht.</span><span class="sxs-lookup"><span data-stu-id="309bf-106">In later lessons, you will use the clustering mining models to explore the different ways in which customers can be grouped, and will use decision tree mining models to predict whether or not a potential customer will purchase a bicycle.</span></span>  
  
## <a name="create-mining-structure-statement"></a><span data-ttu-id="309bf-107">CREATE MINING STRUCTURE-Anweisung</span><span class="sxs-lookup"><span data-stu-id="309bf-107">CREATE MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="309bf-108">Zum Erstellen einer Mining Struktur verwenden Sie die Anweisung [CREATE MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) .</span><span class="sxs-lookup"><span data-stu-id="309bf-108">To create a mining structure, you use the [CREATE MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) statement.</span></span> <span data-ttu-id="309bf-109">Der in der Anweisung enthaltene Code umfasst folgende Abschnitte: </span><span class="sxs-lookup"><span data-stu-id="309bf-109">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="309bf-110">Benennen der-Struktur.</span><span class="sxs-lookup"><span data-stu-id="309bf-110">Naming the structure.</span></span>  
  
-   <span data-ttu-id="309bf-111">Definieren der Schlüssel Spalte.</span><span class="sxs-lookup"><span data-stu-id="309bf-111">Defining the key column.</span></span>  
  
-   <span data-ttu-id="309bf-112">Definieren der Miningspalten</span><span class="sxs-lookup"><span data-stu-id="309bf-112">Defining the mining columns.</span></span>  
  
-   <span data-ttu-id="309bf-113">Definieren eines optionalen Test-Datasets</span><span class="sxs-lookup"><span data-stu-id="309bf-113">Defining an optional testing data set.</span></span>  
  
 <span data-ttu-id="309bf-114">Es folgt ein allgemeines Beispiel für die CREATE MINING STRUCTURE-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="309bf-114">The following is a generic example of the CREATE MINING STRUCTURE statement:</span></span>  
  
```  
CREATE MINING STRUCTURE [<mining structure name>]  
(  
    <key column>,  
    <mining structure columns>  
)   
WITH HOLDOUT (<holdout specifier>)  
```  
  
 <span data-ttu-id="309bf-115">Die erste Codezeile definiert den Namen der Struktur:</span><span class="sxs-lookup"><span data-stu-id="309bf-115">The first line of the code defines the name of the structure:</span></span>  
  
```  
CREATE MINING STRUCTURE [<mining structure name>]  
```  
  
 <span data-ttu-id="309bf-116">Weitere Informationen zum Benennen eines Objekts in Data Mining-Erweiterungen (DMX) finden Sie unter Bezeichner [&#40;DMX-&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="309bf-116">For information about naming an object in Data Mining Extensions (DMX), see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="309bf-117">Die nächste Codezeile definiert die Schlüsselspalte für die Miningstruktur, die eine Entität in den Quelldaten eindeutig identifiziert:</span><span class="sxs-lookup"><span data-stu-id="309bf-117">The next line of the code defines the key column for the mining structure, which uniquely identifies an entity in the source data:</span></span>  
  
```  
<key column>,  
```  
  
 <span data-ttu-id="309bf-118">In der Miningstruktur, die Sie erstellen, definiert der Kundenbezeichner `CustomerKey` eine Entität in den Quelldaten.</span><span class="sxs-lookup"><span data-stu-id="309bf-118">In the mining structure you will create, the customer identifier, `CustomerKey`, defines an entity in the source data.</span></span>  
  
 <span data-ttu-id="309bf-119">Mit der nächsten Codezeile werden die Miningspalten definiert, die von den Miningmodellen verwendet werden, die der Miningstruktur zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="309bf-119">The next line of the code is used to define the mining columns that will be used by the mining models associated with the mining structure:</span></span>  
  
```  
<mining structure columns>  
```  
  
 <span data-ttu-id="309bf-120">Sie können die diskretisieren-Funktion in verwenden \<mining structure columns> , um kontinuierliche Spalten mithilfe der folgenden Syntax diskretisieren:</span><span class="sxs-lookup"><span data-stu-id="309bf-120">You can use the DISCRETIZE function within \<mining structure columns> to discretize continuous columns by using the following syntax:</span></span>  
  
 `DISCRETIZE(<method>,<number of buckets>)`  
  
 <span data-ttu-id="309bf-121">Weitere Informationen zum Diskretisieren von Spalten finden Sie unter [Diskretisierungsmethoden &#40;Data Mining-&#41;](../../2014/analysis-services/data-mining/discretization-methods-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="309bf-121">For more information about discretizing columns, see [Discretization Methods &#40;Data Mining&#41;](../../2014/analysis-services/data-mining/discretization-methods-data-mining.md).</span></span> <span data-ttu-id="309bf-122">Weitere Informationen zu den Typen von Mining Struktur Spalten, die Sie definieren können, finden Sie unter [Mining Struktur Spalten](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span><span class="sxs-lookup"><span data-stu-id="309bf-122">For more information about the types of mining structure columns that you can define, see [Mining Structure Columns](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span></span>  
  
 <span data-ttu-id="309bf-123">In der letzten Codezeile wird eine optionale Partition in der Miningstruktur definiert:</span><span class="sxs-lookup"><span data-stu-id="309bf-123">The final line of the code defines an optional partition in the mining structure:</span></span>  
  
```  
WITH HOLDOUT (<holdout specifier>)  
```  
  
 <span data-ttu-id="309bf-124">Sie geben einen Teil der Daten an, die zum Testen von Miningmodellen verwendet werden sollen, die mit der Struktur verknüpft sind. Die übrigen Daten werden zum Trainieren der Modelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="309bf-124">You specify some portion of the data to use for testing mining models that are related to the structure, and the remaining data is used for training the models.</span></span> <span data-ttu-id="309bf-125">Standardmäßig erstellt [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ein Test-Dataset, das 30 % aller Falldaten enthält.</span><span class="sxs-lookup"><span data-stu-id="309bf-125">By default, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] creates a test data set that contains 30 percent of all case data.</span></span> <span data-ttu-id="309bf-126">Sie fügen die Spezifikation hinzu, dass das Test-Dataset 30 % der Fälle bis zu einem Maximum von 1000 Fällen enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="309bf-126">You will add the specification that the test data set should contain 30 percent of the cases up to a maximum of 1000 cases.</span></span> <span data-ttu-id="309bf-127">Wenn 30 % der Fälle weniger sind als 1000, enthält das Test-Dataset den kleineren Wert.</span><span class="sxs-lookup"><span data-stu-id="309bf-127">If 30 percent of the cases is less than 1000, the test data set will contain the smaller amount.</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="309bf-128">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="309bf-128">Lesson Tasks</span></span>  
 <span data-ttu-id="309bf-129">Im Rahmen dieser Lektion führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="309bf-129">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="309bf-130">Erstellen Sie eine neue leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="309bf-130">Create a new blank query.</span></span>  
  
-   <span data-ttu-id="309bf-131">Ändern Sie die Abfrage, um die Mining Struktur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="309bf-131">Alter the query to create the mining structure.</span></span>  
  
-   <span data-ttu-id="309bf-132">Ausführen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="309bf-132">Execute the query.</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="309bf-133">Erstellen einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="309bf-133">Creating the Query</span></span>  
 <span data-ttu-id="309bf-134">Im ersten Schritt stellen Sie eine Verbindung zu einer Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] her und erstellen eine neue DMX-Abfrage in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="309bf-134">The first step is to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and create a new DMX query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-create-a-new-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="309bf-135">So erstellen Sie eine neue DMX-Abfrage in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="309bf-135">To create a new DMX query in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="309bf-136">Öffnen Sie [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="309bf-136">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="309bf-137">Wählen Sie im Dialogfeld **Verbindung mit Server herstellen** unter **Servertyp**die Option **Analysis Services**aus.</span><span class="sxs-lookup"><span data-stu-id="309bf-137">In the **Connect to Server** dialog box, for **Server type**, select **Analysis Services**.</span></span> <span data-ttu-id="309bf-138">Geben Sie unter **Server Name** `LocalHost` den Namen ein, oder geben Sie den Namen der Instanz von ein, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] mit der Sie für diese Lektion eine Verbindung herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="309bf-138">In **Server name**, type `LocalHost`, or type the name of the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you want to connect to for this lesson.</span></span> <span data-ttu-id="309bf-139">Klicken Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="309bf-139">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="309bf-140">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX** , um den **Abfrage-Editor** und eine neue, leere Abfrage zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="309bf-140">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX** to open the **Query Editor** and a new, blank query.</span></span>  
  
## <a name="altering-the-query"></a><span data-ttu-id="309bf-141">Ändern der Abfrage</span><span class="sxs-lookup"><span data-stu-id="309bf-141">Altering the Query</span></span>  
 <span data-ttu-id="309bf-142">Im nächsten Schritt ändern Sie die oben beschriebene CREATE MINING STRUCTURE-Anweisung und erstellen die Bike Buyer-Miningstruktur.</span><span class="sxs-lookup"><span data-stu-id="309bf-142">The next step is to modify the CREATE MINING STRUCTURE statement described above to create the Bike Buyer mining structure.</span></span>  
  
#### <a name="to-customize-the-create-mining-structure-statement"></a><span data-ttu-id="309bf-143">So passen Sie die CREATE MINING STRUCTURE-Anweisung an</span><span class="sxs-lookup"><span data-stu-id="309bf-143">To customize the CREATE MINING STRUCTURE statement</span></span>  
  
1.  <span data-ttu-id="309bf-144">Kopieren Sie im Abfrage-Editor das allgemeine Beispiel der CREATE MINING STRUCTURE-Anweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="309bf-144">In the Query Editor, copy the generic example of the CREATE MINING STRUCTURE statement into the blank query.</span></span>  
  
2.  <span data-ttu-id="309bf-145">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="309bf-145">Replace the following:</span></span>  
  
    ```  
    [<mining structure>]   
    ```  
  
     <span data-ttu-id="309bf-146">durch:</span><span class="sxs-lookup"><span data-stu-id="309bf-146">with:</span></span>  
  
    ```  
    [Bike Buyer]  
    ```  
  
3.  <span data-ttu-id="309bf-147">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="309bf-147">Replace the following:</span></span>  
  
    ```  
    <key column>   
    ```  
  
     <span data-ttu-id="309bf-148">durch:</span><span class="sxs-lookup"><span data-stu-id="309bf-148">with:</span></span>  
  
    ```  
    CustomerKey LONG KEY  
    ```  
  
4.  <span data-ttu-id="309bf-149">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="309bf-149">Replace the following:</span></span>  
  
    ```  
    <mining structure columns>   
    ```  
  
     <span data-ttu-id="309bf-150">durch:</span><span class="sxs-lookup"><span data-stu-id="309bf-150">with:</span></span>  
  
    ```  
    [Age] LONG DISCRETIZED(Automatic,10),  
    [Bike Buyer] LONG DISCRETE,  
    [Commute Distance] TEXT DISCRETE,  
    [Education] TEXT DISCRETE,  
    [Gender] TEXT DISCRETE,  
    [House Owner Flag] TEXT DISCRETE,  
    [Marital Status] TEXT DISCRETE,  
    [Number Cars Owned] LONG DISCRETE,  
    [Number Children At Home] LONG DISCRETE,  
    [Occupation] TEXT DISCRETE,  
    [Region] TEXT DISCRETE,  
    [Total Children]LONG DISCRETE,  
    [Yearly Income] DOUBLE CONTINUOUS  
    ```  
  
5.  <span data-ttu-id="309bf-151">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="309bf-151">Replace the following:</span></span>  
  
    ```  
    WITH HOLDOUT (holdout specifier>)  
    ```  
  
     <span data-ttu-id="309bf-152">durch:</span><span class="sxs-lookup"><span data-stu-id="309bf-152">with:</span></span>  
  
    ```  
    WITH HOLDOUT (30 PERCENT or 1000 CASES)  
    ```  
  
     <span data-ttu-id="309bf-153">Die gesamte Miningstrukturanweisung sollte jetzt wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="309bf-153">The complete mining structure statement should now be as follows:</span></span>  
  
    ```  
    CREATE MINING STRUCTURE [Bike Buyer]  
    (  
       [Customer Key] LONG KEY,  
       [Age]LONG DISCRETIZED(Automatic,10),  
       [Bike Buyer] LONG DISCRETE,  
       [Commute Distance] TEXT DISCRETE,  
       [Education] TEXT DISCRETE,  
       [Gender] TEXT DISCRETE,  
       [House Owner Flag] TEXT DISCRETE,  
       [Marital Status] TEXT DISCRETE,  
       [Number Cars Owned]LONG DISCRETE,  
       [Number Children At Home]LONG DISCRETE,  
       [Occupation] TEXT DISCRETE,  
       [Region] TEXT DISCRETE,  
       [Total Children]LONG DISCRETE,  
       [Yearly Income] DOUBLE CONTINUOUS  
    )  
    WITH HOLDOUT (30 PERCENT or 1000 CASES)  
  
    ```  
  
6.  <span data-ttu-id="309bf-154">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="309bf-154">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
7.  <span data-ttu-id="309bf-155">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `Bike Buyer Structure.dmx` .</span><span class="sxs-lookup"><span data-stu-id="309bf-155">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Bike Buyer Structure.dmx`.</span></span>  
  
## <a name="executing-the-query"></a><span data-ttu-id="309bf-156">Ausführen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="309bf-156">Executing the Query</span></span>  
 <span data-ttu-id="309bf-157">Im letzten Schritt führen Sie die Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="309bf-157">The final step is to execute the query.</span></span> <span data-ttu-id="309bf-158">Nachdem eine Abfrage erstellt und gespeichert wurde, muss sie ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="309bf-158">After a query is created and saved, it needs to be executed.</span></span> <span data-ttu-id="309bf-159">Das bedeutet, die Anweisung muss ausgeführt werden, um auf dem Server eine Miningstruktur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="309bf-159">That is, the statement needs to be run in order to create the mining structure on the server.</span></span> <span data-ttu-id="309bf-160">Weitere Informationen zum Ausführen von Abfragen im Abfrage-Editor finden Sie unter [Datenbank-Engine-Abfrage-Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="309bf-160">For more information about executing queries in Query Editor, see [Database Engine Query Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="309bf-161">So führen Sie die Abfrage aus</span><span class="sxs-lookup"><span data-stu-id="309bf-161">To execute the query</span></span>  
  
1.  <span data-ttu-id="309bf-162">Klicken Sie im Abfrage-Editor auf der Symbolleiste auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="309bf-162">In Query Editor, on the toolbar, click **Execute**.</span></span>  
  
     <span data-ttu-id="309bf-163">Der Status der Abfrage wird auf der Registerkarte **Nachrichten** unten im Abfrage-Editor angezeigt, nachdem die Ausführung der Anweisung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="309bf-163">The status of the query is displayed in the **Messages** tab at the bottom of Query Editor after the statement finishes executing.</span></span> <span data-ttu-id="309bf-164">Die Meldung sollte Folgendes anzeigen:</span><span class="sxs-lookup"><span data-stu-id="309bf-164">Messages should display:</span></span>  
  
    ```  
    Executing the query   
    Execution complete  
    ```  
  
     <span data-ttu-id="309bf-165">Eine neue Struktur mit dem Namen **Bike Buyer** ist jetzt auf dem Server vorhanden.</span><span class="sxs-lookup"><span data-stu-id="309bf-165">A new structure named **Bike Buyer** now exists on the server.</span></span>  
  
 <span data-ttu-id="309bf-166">In der nächsten Lektion fügen Sie der soeben erstellten Struktur Miningmodelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="309bf-166">In the next lesson, you will add mining models to the structure you just created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="309bf-167">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="309bf-167">Next Lesson</span></span>  
 [<span data-ttu-id="309bf-168">Lektion 2: Hinzufügen von Miningmodellen zur Bike Buyer-Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="309bf-168">Lesson 2: Adding Mining Models to the Bike Buyer Mining Structure</span></span>](../../2014/tutorials/lesson-2-adding-mining-models-to-the-bike-buyer-mining-structure.md)  
  
  
