---
title: Hinzufügen einer Datenquellen Sicht mit einer Liste von Tabellen (Data Mining-Lernprogramm für Fortgeschrittene) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a14cd7f1-7a10-4ec6-af6a-f5f0676a0308
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: da1a9bff093e0b59e9d1166554d95bcf61aded08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720548"
---
# <a name="adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial"></a><span data-ttu-id="51216-102">Hinzufügen einer Datenquellensicht mit geschachtelten Tabellen (Data Mining-Lernprogramm für Fortgeschrittene)</span><span class="sxs-lookup"><span data-stu-id="51216-102">Adding a Data Source View with Nested Tables (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="51216-103">Zum Erstellen eines Warenkorbmodells müssen Sie eine Datenquellensicht verwenden, die assoziative Daten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="51216-103">To create a market basket model, you must use a data source view that supports associative data.</span></span> <span data-ttu-id="51216-104">Diese Datenquellensicht wird auch für das Sequenzclusterszenario verwendet.</span><span class="sxs-lookup"><span data-stu-id="51216-104">This data source view will also be used for the sequence clustering scenario.</span></span>  
  
 <span data-ttu-id="51216-105">Diese Datenquellen Sicht unterscheidet sich von anderen, mit denen Sie möglicherweise gearbeitet haben, da Sie eine *Tabelle*enthält.</span><span class="sxs-lookup"><span data-stu-id="51216-105">This data source view is different from others that you may have worked with because it contains a *nested table*.</span></span> <span data-ttu-id="51216-106">Eine Tabellen *Tabelle* ist eine Tabelle, die mehrere Zeilen mit Informationen zu einer einzelnen Zeile in der Fall Tabelle enthält.</span><span class="sxs-lookup"><span data-stu-id="51216-106">A *nested table* is a table that contains multiple rows of information about a single row in the case table.</span></span> <span data-ttu-id="51216-107">Wenn das Modell beispielsweise das Kaufverhalten von Kunden analysiert, würden Sie als Falltabelle in der Regel eine Tabelle verwenden, die eine eindeutige Zeile für jeden Kunden enthält.</span><span class="sxs-lookup"><span data-stu-id="51216-107">For example, if your model analyzes the purchasing behavior of customers, you would typically use a table that has a unique row for each customer as the case table.</span></span> <span data-ttu-id="51216-108">Es kann jedoch vorkommen, dass ein Kunde mehrere Käufe tätigt und Sie die Sequenz der Käufe oder Produkte analysieren möchten, die häufig zusammen gekauft werden.</span><span class="sxs-lookup"><span data-stu-id="51216-108">However, each customer might make multiple purchases, and you might want to analyze the sequence of purchases, or products that are frequently purchased together.</span></span> <span data-ttu-id="51216-109">Um diese Käufe im Modell logisch darzustellen, fügen Sie der Datenquellensicht, in der die Käufe jedes Kunden aufgeführt werden, eine weitere Tabelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="51216-109">To logically represent these purchases in your model, you add another table to the data source view that lists the purchases for each customer.</span></span>  
  
 <span data-ttu-id="51216-110">Diese geschachtelte Tabelle ist über eine n:1-Beziehung mit der Kundentabelle verknüpft.</span><span class="sxs-lookup"><span data-stu-id="51216-110">This nested purchases table is related to the customer table by a many-to-one relationship.</span></span> <span data-ttu-id="51216-111">Die geschachtelte Tabelle kann mehrere Zeilen für jeden Kunden enthalten, wobei jede Zeile ein einzelnes Produkt enthält, das gekauft wurde, ggf. mit weiteren Informationen zur Reihenfolge der Einkäufe, zum Verkaufspreis oder zu gewährten Rabatten.</span><span class="sxs-lookup"><span data-stu-id="51216-111">The nested table might contain many rows for each customer, each row containing a single product that was purchased, perhaps with additional information about the order that the purchases were made, the price at the time of the order, or any promotions that applied.</span></span> <span data-ttu-id="51216-112">Sie können die Informationen in der geschachtelten Tabelle als Eingaben für das Modell oder als vorhersagbares Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="51216-112">You can use the information in the nested table as inputs to the model, or as the predictable attribute.</span></span>  
  
 <span data-ttu-id="51216-113">In dieser Lektion führen Sie die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="51216-113">In this lesson, you do the following tasks:</span></span>  
  
-   <span data-ttu-id="51216-114">Sie fügen der Datenquelle eine Datenquellen Sicht hinzu [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="51216-114">You add a data source view to the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] data source.</span></span>  
  
-   <span data-ttu-id="51216-115">Sie fügen dieser Sicht die Falltabelle und die geschachtelte Tabelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="51216-115">You add the case and nested tables to this view.</span></span>  
  
-   <span data-ttu-id="51216-116">Sie geben die n:1-Beziehung zwischen der Falltabelle und der geschachtelten Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="51216-116">You specify the many-to-one relationship between the case and nested table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="51216-117">.</span><span class="sxs-lookup"><span data-stu-id="51216-117">.</span></span> <span data-ttu-id="51216-118">Es ist wichtig, dass Sie die beschriebene Prozedur genau befolgen, um die Beziehung zwischen der Falltabelle und der geschachtelten Tabelle korrekt zu definieren und Fehler bei der Verarbeitung des Modells zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="51216-118">It is important that you follow the described procedure exactly, to correctly specify the relationship between the case table and the nested table and to avoid errors when you process the model.</span></span>  
  
-   <span data-ttu-id="51216-119">Sie definieren, wie die Datenspalten im Modell verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="51216-119">You define how the columns of data are used in the model.</span></span>  
  
 <span data-ttu-id="51216-120">Weitere Informationen zum Arbeiten mit Case-und netsted-Tabellen und zum Auswählen einer Schlüssel Tabelle für eine Schlüssel Tabelle finden Sie unter [&#40;von Analysis Services Data Mining-&#41;](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="51216-120">For more information about working with case and nested tables, and how to choose a nested table key, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/nested-tables-analysis-services-data-mining.md).</span></span>  
  
### <a name="to-add-a-data-source-view"></a><span data-ttu-id="51216-121">So fügen Sie eine Datenquellensicht hinzu</span><span class="sxs-lookup"><span data-stu-id="51216-121">To add a data source view</span></span>  
  
1.  <span data-ttu-id="51216-122">Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf **Datenquellen Sichten**, und wählen Sie dann **neue Datenquellen Sicht**aus.</span><span class="sxs-lookup"><span data-stu-id="51216-122">In Solution Explorer, right-click **Data Source Views**, and then select **New Data Source View**.</span></span>  
  
     <span data-ttu-id="51216-123">Der Datenquellensicht-Assistent wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="51216-123">The Data Source View Wizard opens.</span></span>  
  
2.  <span data-ttu-id="51216-124">Klicken Sie auf der Seite **Willkommen beim Datenquellensicht-Assistenten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="51216-124">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="51216-125">Wählen Sie auf der Seite **Datenquelle auswählen** unter **relationale Datenquellen**die Datenquelle aus, die [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] Sie im Lernprogramm zu Data Mining-Grundlagen erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="51216-125">On the **Select a Data Source** page, under **Relational data sources**, select the [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] data source that you created in the Basic Data Mining Tutorial.</span></span> <span data-ttu-id="51216-126">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="51216-126">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="51216-127">Wählen Sie auf der Seite **Tabellen und Sichten auswählen** die folgenden Tabellen aus, und klicken Sie dann auf den Pfeil nach rechts, um Sie in die neue Datenquellen Sicht einzuschließen:</span><span class="sxs-lookup"><span data-stu-id="51216-127">On the **Select Tables and Views** page, select the following tables, and then click the right arrow to include them in the new data source view:</span></span>  
  
    -   `vAssocSeqOrders`  
  
    -   `vAssocSeqLineItems`  
  
5.  <span data-ttu-id="51216-128">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="51216-128">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="51216-129">Auf der Seite **Assistenten abschließen** wird die Datenquellen Sicht standardmäßig benannt [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="51216-129">On the **Completing the Wizard** page, by default the data source view is named [!INCLUDE[ssAWDWsp](../includes/ssawdwsp-md.md)].</span></span> <span data-ttu-id="51216-130">Ändern Sie den Namen in `Orders` , und klicken Sie dann auf **Fertig**stellen.</span><span class="sxs-lookup"><span data-stu-id="51216-130">Change the name to `Orders`, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="51216-131">Der Datenquellen Sicht-Designer wird geöffnet, und die `Orders` Datenquellen Sicht wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="51216-131">Data Source View Designer opens and the `Orders` data source view appears.</span></span>  
  
### <a name="to-create-a-relationship-between-tables"></a><span data-ttu-id="51216-132">So erstellen Sie eine Beziehung zwischen Tabellen</span><span class="sxs-lookup"><span data-stu-id="51216-132">To create a relationship between tables</span></span>  
  
1.  <span data-ttu-id="51216-133">Positionieren Sie die beiden Tabellen im Datenquellensicht-Designer horizontal nebeneinander, sodass sich die Tabelle vAssocSeqLineItems links und die Tabelle vAssocSeqOrders rechts befindet.</span><span class="sxs-lookup"><span data-stu-id="51216-133">In Data Source View Designer, position the two tables so that the tables are aligned horizontally, with the vAssocSeqLineItems table on the left side and the vAssocSeqOrders table on the right side.</span></span>  
  
2.  <span data-ttu-id="51216-134">Wählen Sie die Spalte **OrderNumber** in der Tabelle vassocsetqlineitems aus.</span><span class="sxs-lookup"><span data-stu-id="51216-134">Select the **OrderNumber** column in the vAssocSeqLineItems table.</span></span>  
  
3.  <span data-ttu-id="51216-135">Ziehen Sie die Spalte in die Tabelle vassocsetqorders, und legen Sie Sie in der Spalte **OrderNumber** ab.</span><span class="sxs-lookup"><span data-stu-id="51216-135">Drag the column to the vAssocSeqOrders table, and put it on the **OrderNumber** column.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="51216-136">Stellen Sie sicher, dass Sie die Spalte **OrderNumber** aus der in der Tabelle vassocsetqlineitems dargestellten Tabelle, die die n-Seite des Joins darstellt, in die Fall Tabelle vassocsetqorders ziehen, die die 1-Seite des Joins darstellt.</span><span class="sxs-lookup"><span data-stu-id="51216-136">Make sure to drag the **OrderNumber** column from the vAssocSeqLineItems nested table, which represents the many side of the join, to the vAssocSeqOrders case table, which represents the one side of the join.</span></span>  
  
     <span data-ttu-id="51216-137">Zwischen den *many-to-one relationship* Tabellen vassoccot qlineitems und vassocssqorders besteht jetzt eine neue m:1-Beziehung.</span><span class="sxs-lookup"><span data-stu-id="51216-137">A new *many-to-one relationship* now exists between the vAssocSeqLineItems and vAssocSeqOrders tables.</span></span> <span data-ttu-id="51216-138">Wenn Sie die Tabellen ordnungsgemäß verknüpft haben, sollte die Datenquellensicht wie folgt angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="51216-138">If you have joined the tables correctly, the data source view should appear as follows:</span></span>  
  
     <span data-ttu-id="51216-139">![Erwarteter m:1-Join für geschachtelte Tabelle und Falltabelle](../../2014/tutorials/media/dsv-nestedjoin-illustration.gif "Erwarteter m:1-Join für geschachtelte Tabelle und Falltabelle")</span><span class="sxs-lookup"><span data-stu-id="51216-139">![expected many-to-one join on nested and case table](../../2014/tutorials/media/dsv-nestedjoin-illustration.gif "expected many-to-one join on nested and case table")</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="51216-140">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="51216-140">Next Task in Lesson</span></span>  
 [<span data-ttu-id="51216-141">Erstellen einer Market Basket-Struktur und eines Modells &#40;Data Mining-Lernprogramm für fortgeschrittene&#41;</span><span class="sxs-lookup"><span data-stu-id="51216-141">Creating a Market Basket Structure and Model &#40;Intermediate Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-market-basket-structure-and-model-intermediate-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="51216-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51216-142">See Also</span></span>  
 <span data-ttu-id="51216-143">[Data Mining-Lernprogramm für fortgeschrittene &#40;Analysis Services-Data Mining-&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="51216-143">[Intermediate Data Mining Tutorial &#40;Analysis Services - Data Mining&#41;](../../2014/tutorials/intermediate-data-mining-tutorial-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="51216-144">[Mining Strukturen &#40;Analysis Services Data Mining-&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="51216-144">[Mining Structures &#40;Analysis Services - Data Mining&#41;](../../2014/analysis-services/data-mining/mining-structures-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="51216-145">Miningmodelle &#40;Analysis Services – Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="51216-145">Mining Models &#40;Analysis Services - Data Mining&#41;</span></span>](../../2014/analysis-services/data-mining/mining-models-analysis-services-data-mining.md)  
  
  
