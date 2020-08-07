---
title: 'Lektion 1: Erstellen der Market Basket-Mining Struktur | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a817c8d1-aff4-42b4-b194-ad9cc1c60f35
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: a6a6e123e525512a72d70bcc8ca2eba549d1347e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719099"
---
# <a name="lesson-1-creating-the-market-basket-mining-structure"></a><span data-ttu-id="2e9b4-102">Lektion 1: Erstellen der Market Basket-Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="2e9b4-102">Lesson 1: Creating the Market Basket Mining Structure</span></span>
  <span data-ttu-id="2e9b4-103">In dieser Lektion erstellen Sie eine Miningstruktur, mit der sich vorhersagen lässt, welche [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)]-Produkte ein Kunde tendenziell als Kombinationskauf erwirbt.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-103">In this lesson, you will create a mining structure that allows you to predict what [!INCLUDE[ssSampleDBCoFull](../includes/sssampledbcofull-md.md)] products a customer tends to purchase at the same time.</span></span> <span data-ttu-id="2e9b4-104">Wenn Sie mit Mining Strukturen und deren Rolle in Data Mining nicht vertraut sind, finden Sie weitere Informationen unter [Mining Strukturen &#40;Analysis Services Data Mining-&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="2e9b4-104">If you are unfamiliar with mining structures and their role in data mining, see [Mining Structures &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md).</span></span>  
  
 <span data-ttu-id="2e9b4-105">Die Association-Mining Struktur, die Sie in dieser Lektion erstellen, unterstützt das Hinzufügen von Mining Modellen auf der Grundlage des [Microsoft Association-Algorithmus](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md).</span><span class="sxs-lookup"><span data-stu-id="2e9b4-105">The association mining structure that you will create in this lesson supports adding mining models based on the [Microsoft Association Algorithm](../../2014/analysis-services/data-mining/microsoft-association-algorithm.md).</span></span> <span data-ttu-id="2e9b4-106">In späteren Lektionen verwenden Sie die Miningmodelle, um vorherzusagen, welche Produkttypen ein Kunde tendenziell als Kombinationskauf erwirbt. Dieses Verfahren wird als Warenkorbanalyse bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-106">In later lessons, you will use the mining models to predict the type of products a customer tends to purchase at the same time, which is called a market basket analysis.</span></span> <span data-ttu-id="2e9b4-107">So könnten Sie beispielsweise zu dem Ergebnis kommen, dass Kunden tendenziell gleichzeitig Mountainbikes, Fahrradreifen und Helme kaufen.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-107">For example, you may find that customers tend to buy mountain bikes, bike tires, and helmets at the same time.</span></span>  
  
 <span data-ttu-id="2e9b4-108">In dieser Lektion wird die Miningstruktur mithilfe von geschachtelten Tabellen definiert.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-108">In this lesson, the mining structure is defined by using nested tables.</span></span> <span data-ttu-id="2e9b4-109">Geschachtelte Tabellen werden deshalb verwendet, weil die Datendomäne, die durch die Struktur definiert wird, in zwei verschiedenen Quelltabellen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-109">Nested tables are used because the data domain that will be defined by the structure is contained within two different source tables.</span></span> <span data-ttu-id="2e9b4-110">Weitere Informationen zu den Tabellen finden Sie unter [Tabellen &#40;Analysis Services Data Mining-&#41;](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="2e9b4-110">For more information on nested tables, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span></span>  
  
## <a name="create-mining-structure-statement"></a><span data-ttu-id="2e9b4-111">CREATE MINING STRUCTURE-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2e9b4-111">CREATE MINING STRUCTURE Statement</span></span>  
 <span data-ttu-id="2e9b4-112">Um eine Mining Struktur zu erstellen, die eine Tabellen Tabelle enthält, verwenden Sie die Anweisung [CREATE MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) .</span><span class="sxs-lookup"><span data-stu-id="2e9b4-112">In order to create a mining structure containing a nested table, you use the [CREATE MINING STRUCTURE &#40;DMX&#41;](/sql/dmx/create-mining-structure-dmx) statement.</span></span> <span data-ttu-id="2e9b4-113">Der in der Anweisung enthaltene Code umfasst folgende Abschnitte: </span><span class="sxs-lookup"><span data-stu-id="2e9b4-113">The code in the statement can be broken into the following parts:</span></span>  
  
-   <span data-ttu-id="2e9b4-114">Benennen der Struktur</span><span class="sxs-lookup"><span data-stu-id="2e9b4-114">Naming the structure</span></span>  
  
-   <span data-ttu-id="2e9b4-115">Definieren der Schlüsselspalte</span><span class="sxs-lookup"><span data-stu-id="2e9b4-115">Defining the key column</span></span>  
  
-   <span data-ttu-id="2e9b4-116">Definieren der Mining Spalten</span><span class="sxs-lookup"><span data-stu-id="2e9b4-116">Defining the mining columns</span></span>  
  
-   <span data-ttu-id="2e9b4-117">Definieren der Spalten der geschachtelten Tabellen</span><span class="sxs-lookup"><span data-stu-id="2e9b4-117">Defining the nested table columns</span></span>  
  
 <span data-ttu-id="2e9b4-118">Es folgt ein allgemeines Beispiel für die CREATE MINING STRUCTURE-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="2e9b4-118">The following is a generic example of the CREATE MINING STRUCTURE statement:</span></span>  
  
```  
CREATE MINING STRUCTURE [<Mining Structure Name>]  
(  
   <key column>,  
   <mining structure columns>,  
   <table columns>  
   (  <nested key column>,  
      <nested mining structure columns> )  
)  
  
```  
  
 <span data-ttu-id="2e9b4-119">Die erste Codezeile definiert den Namen der Struktur:</span><span class="sxs-lookup"><span data-stu-id="2e9b4-119">The first line of the code defines the name of the structure:</span></span>  
  
```  
CREATE MINING STRUCTURE [Mining Structure Name]  
```  
  
 <span data-ttu-id="2e9b4-120">Weitere Informationen zum Benennen eines Objekts in DMX finden Sie unter Bezeichner [&#40;DMX-&#41;](/sql/dmx/identifiers-dmx).</span><span class="sxs-lookup"><span data-stu-id="2e9b4-120">For information about naming an object in DMX, see [Identifiers &#40;DMX&#41;](/sql/dmx/identifiers-dmx).</span></span>  
  
 <span data-ttu-id="2e9b4-121">Die nächste Codezeile definiert die Schlüsselspalte für die Miningstruktur, die eine Entität in den Quelldaten eindeutig identifiziert:</span><span class="sxs-lookup"><span data-stu-id="2e9b4-121">The next line of the code defines the key column for the mining structure, which uniquely identifies an entity in the source data:</span></span>  
  
```  
<key column>  
```  
  
 <span data-ttu-id="2e9b4-122">Mit der nächsten Codezeile werden die Miningspalten definiert, die von den Miningmodellen verwendet werden, die der Miningstruktur zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="2e9b4-122">The next line of the code is used to define the mining columns that will be used by the mining models associated with the mining structure:</span></span>  
  
```  
<mining structure columns>  
```  
  
 <span data-ttu-id="2e9b4-123">Die nächsten Codezeilen definieren die Spalten der geschachtelten Tabellen:</span><span class="sxs-lookup"><span data-stu-id="2e9b4-123">The next lines of the code define the nested table columns:</span></span>  
  
```  
<table columns>  
(  <nested key column>,  
   <nested mining structure columns> )  
```  
  
 <span data-ttu-id="2e9b4-124">Informationen zu den Typen von Mining Struktur Spalten, die Sie definieren können, finden Sie unter [Mining Struktur Spalten](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span><span class="sxs-lookup"><span data-stu-id="2e9b4-124">For information about the types of mining structure columns that you can define, see [Mining Structure Columns](../../2014/analysis-services/data-mining/mining-structure-columns.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2e9b4-125">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] erstellt standardmäßig ein zu 30 % zurückgehaltenes Dataset für jede Miningstruktur. Wenn Sie jedoch DMX zum Erstellen einer Miningstruktur verwenden, müssen Sie das zurückgehaltene Dataset (falls gewünscht) manuell hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-125">By default, [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] creates a 30 percent holdout data set for each mining structure; however, when you use DMX to create a mining structure, you must manually add the holdout data set, if desired.</span></span>  
  
## <a name="lesson-tasks"></a><span data-ttu-id="2e9b4-126">Lektionsaufgaben</span><span class="sxs-lookup"><span data-stu-id="2e9b4-126">Lesson Tasks</span></span>  
 <span data-ttu-id="2e9b4-127">Im Rahmen dieser Lektion führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="2e9b4-127">You will perform the following tasks in this lesson:</span></span>  
  
-   <span data-ttu-id="2e9b4-128">Erstellen einer neuen leeren Abfrage</span><span class="sxs-lookup"><span data-stu-id="2e9b4-128">Create a new blank query</span></span>  
  
-   <span data-ttu-id="2e9b4-129">Ändern der Abfrage, um die Miningstruktur zu erstellen</span><span class="sxs-lookup"><span data-stu-id="2e9b4-129">Alter the query to create the mining structure</span></span>  
  
-   <span data-ttu-id="2e9b4-130">Ausführen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="2e9b4-130">Execute the query</span></span>  
  
## <a name="creating-the-query"></a><span data-ttu-id="2e9b4-131">Erstellen einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="2e9b4-131">Creating the Query</span></span>  
 <span data-ttu-id="2e9b4-132">Im ersten Schritt stellen Sie eine Verbindung zu einer Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] her und erstellen eine neue DMX-Abfrage in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e9b4-132">The first step is to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and create a new DMX query in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-create-a-new-dmx-query-in-sql-server-management-studio"></a><span data-ttu-id="2e9b4-133">So erstellen Sie eine neue DMX-Abfrage in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2e9b4-133">To create a new DMX query in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="2e9b4-134">Öffnen Sie [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e9b4-134">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="2e9b4-135">Wählen Sie im Dialogfeld **Verbindung mit Server herstellen** unter **Servertyp**die Option **Analysis Services**aus.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-135">In the **Connect to Server** dialog box, for **Server type**, select **Analysis Services**.</span></span> <span data-ttu-id="2e9b4-136">Geben Sie unter **Server Name**den Namen ein `LocalHost` , oder geben Sie den Namen der Instanz von ein, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] mit der Sie für diese Lektion eine Verbindung herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-136">In **Server name**, type `LocalHost`, or the name of the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you want to connect to for this lesson.</span></span> <span data-ttu-id="2e9b4-137">Klicken Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-137">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="2e9b4-138">Klicken Sie in **Objekt-Explorer**mit der rechten Maustaste auf die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , zeigen Sie auf **neue Abfrage**, und klicken Sie dann auf **DMX**.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-138">In **Object Explorer**, right-click the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], point to **New Query**, and then click **DMX**.</span></span>  
  
     <span data-ttu-id="2e9b4-139">Der Abfrage-Editor wird mit einer neuen leeren Abfrage geöffnet.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-139">Query Editor opens and contains a new, blank query.</span></span>  
  
## <a name="altering-the-query"></a><span data-ttu-id="2e9b4-140">Ändern der Abfrage</span><span class="sxs-lookup"><span data-stu-id="2e9b4-140">Altering the Query</span></span>  
 <span data-ttu-id="2e9b4-141">Im nächsten Schritt ändern Sie die oben beschriebene CREATE MINING STRUCTURE-Anweisung und erstellen die Market Basket-Miningstruktur.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-141">The next step is to modify the CREATE MINING STRUCTURE statement described above to create the Market Basket mining structure.</span></span>  
  
#### <a name="to-customize-the-create-mining-structure-statement"></a><span data-ttu-id="2e9b4-142">So passen Sie die CREATE MINING STRUCTURE-Anweisung an</span><span class="sxs-lookup"><span data-stu-id="2e9b4-142">To customize the CREATE MINING STRUCTURE statement</span></span>  
  
1.  <span data-ttu-id="2e9b4-143">Kopieren Sie im Abfrage-Editor das allgemeine Beispiel der CREATE MINING STRUCTURE-Anweisung in die leere Abfrage.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-143">In Query Editor, copy the generic example of the CREATE MINING STRUCTURE statement into the blank query.</span></span>  
  
2.  <span data-ttu-id="2e9b4-144">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2e9b4-144">Replace the following:</span></span>  
  
    ```  
    [mining structure name]   
    ```  
  
     <span data-ttu-id="2e9b4-145">durch:</span><span class="sxs-lookup"><span data-stu-id="2e9b4-145">with:</span></span>  
  
    ```  
    [Market Basket]  
    ```  
  
3.  <span data-ttu-id="2e9b4-146">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2e9b4-146">Replace the following:</span></span>  
  
    ```  
    <key column>  
    ```  
  
     <span data-ttu-id="2e9b4-147">durch:</span><span class="sxs-lookup"><span data-stu-id="2e9b4-147">with:</span></span>  
  
    ```  
    OrderNumber TEXT KEY  
    ```  
  
4.  <span data-ttu-id="2e9b4-148">Ersetzen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2e9b4-148">Replace the following:</span></span>  
  
    ```  
    <table columns>  
    (  <nested key column>,  
       <nested mining structure columns> )  
    ```  
  
     <span data-ttu-id="2e9b4-149">durch:</span><span class="sxs-lookup"><span data-stu-id="2e9b4-149">with:</span></span>  
  
    ```  
    [Products] TABLE (  
        [Model] TEXT KEY  
    )  
    ```  
  
     <span data-ttu-id="2e9b4-150">Die TEXT KEY-Sprache gibt an, dass die Model-Spalte die Schlüsselspalte für die geschachtelte Tabelle ist.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-150">The TEXT KEY language specifies that the Model column is the key column for the nested table.</span></span>  
  
     <span data-ttu-id="2e9b4-151">Die gesamte Miningstrukturanweisung sollte jetzt wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="2e9b4-151">The complete mining structure statement should now be as follows:</span></span>  
  
    ```  
    CREATE MINING STRUCTURE [Market Basket] (  
        OrderNumber TEXT KEY,  
        [Products] TABLE (  
            [Model] TEXT KEY  
        )  
    )  
    ```  
  
5.  <span data-ttu-id="2e9b4-152">Klicken Sie im Menü **Datei** auf **DMXQuery1. DMX speichern**unter.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-152">On the **File** menu, click **Save DMXQuery1.dmx As**.</span></span>  
  
6.  <span data-ttu-id="2e9b4-153">Navigieren Sie im Dialogfeld **Speichern** unter in den entsprechenden Ordner, und benennen Sie die Datei `Market Basket Structure.dmx` .</span><span class="sxs-lookup"><span data-stu-id="2e9b4-153">In the **Save As** dialog box, browse to the appropriate folder, and name the file `Market Basket Structure.dmx`.</span></span>  
  
## <a name="executing-the-query"></a><span data-ttu-id="2e9b4-154">Ausführen der Abfrage</span><span class="sxs-lookup"><span data-stu-id="2e9b4-154">Executing the Query</span></span>  
 <span data-ttu-id="2e9b4-155">Im letzten Schritt führen Sie die Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-155">The final step is to execute the query.</span></span> <span data-ttu-id="2e9b4-156">Nachdem Sie eine Abfrage erstellt und gespeichert haben, muss sie (d. h. die Anweisung) ausgeführt werden, damit die Miningstruktur auf dem Server erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-156">After a query is created and saved, it needs to be executed (that is, the statement needs to be run) in order to create the mining structure on the server.</span></span> <span data-ttu-id="2e9b4-157">Weitere Informationen zum Ausführen von Abfragen im Abfrage-Editor finden Sie unter [Datenbank-Engine-Abfrage-Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="2e9b4-157">For more information about executing queries in Query Editor, see [Database Engine Query Editor &#40;SQL Server Management Studio&#41;](../relational-databases/scripting/database-engine-query-editor-sql-server-management-studio.md).</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="2e9b4-158">So führen Sie die Abfrage aus</span><span class="sxs-lookup"><span data-stu-id="2e9b4-158">To execute the query</span></span>  
  
-   <span data-ttu-id="2e9b4-159">Klicken Sie im Abfrage-Editor auf der Symbolleiste auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-159">In Query Editor, on the toolbar, click **Execute**.</span></span>  
  
     <span data-ttu-id="2e9b4-160">Der Status der Abfrage wird auf der Registerkarte **Nachrichten** unten im Abfrage-Editor angezeigt, nachdem die Ausführung der Anweisung abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-160">The status of the query is displayed in the **Messages** tab at the bottom of Query Editor after the statement finishes executing.</span></span> <span data-ttu-id="2e9b4-161">Die Meldung sollte Folgendes anzeigen:</span><span class="sxs-lookup"><span data-stu-id="2e9b4-161">Messages should display:</span></span>  
  
    ```  
    Executing the query   
    Execution complete  
    ```  
  
     <span data-ttu-id="2e9b4-162">Eine neue Struktur mit dem Namen **Market Basket** ist jetzt auf dem Server vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-162">A new structure named **Market Basket** now exists on the server.</span></span>  
  
 <span data-ttu-id="2e9b4-163">In der nächsten Lektion fügen Sie der soeben erstellten Market Basket-Miningstruktur Miningmodelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="2e9b4-163">In the next lesson, you will add mining models to the Market Basket mining structure you just created.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="2e9b4-164">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="2e9b4-164">Next Lesson</span></span>  
 [<span data-ttu-id="2e9b4-165">Lektion 2: Hinzufügen von Miningmodellen zur Market Basket-Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="2e9b4-165">Lesson 2: Adding Mining Models to the Market Basket Mining Structure</span></span>](../../2014/tutorials/lesson-2-adding-mining-models-to-the-market-basket-mining-structure.md)  
  
  
