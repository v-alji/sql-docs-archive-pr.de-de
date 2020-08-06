---
title: Erstellen einer Sequence Clustering-Mining Modellstruktur (Data Mining-Lernprogramm für Fortgeschrittene) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: e9339227-6c2e-4c4b-8be2-8c1960bc4a8d
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 37d0a1738a758a9d8c4fd6b80310037937a9803f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616292"
---
# <a name="creating-a-sequence-clustering-mining-model-structure-intermediate-data-mining-tutorial"></a><span data-ttu-id="648a4-102">Erstellen einer Sequence Clustering-Miningmodellstruktur (Mittleres Data Mining Tutorial)</span><span class="sxs-lookup"><span data-stu-id="648a4-102">Creating a Sequence Clustering Mining Model Structure (Intermediate Data Mining Tutorial)</span></span>
  <span data-ttu-id="648a4-103">Der erste Schritt zum Erstellen eines Sequenzcluster-Miningmodells besteht im Erstellen einer neuen Miningstruktur sowie eines neuen Miningmodells auf der Basis des [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering-Algorithmus mittels des Data Mining-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="648a4-103">The first step in creating a sequence clustering mining model is to use the Data Mining Wizard to create a new mining structure and a mining model based on the [!INCLUDE[msCoName](../includes/msconame-md.md)] Sequence Clustering algorithm.</span></span>  
  
 <span data-ttu-id="648a4-104">Dazu verwenden Sie die gleiche Datenquellensicht wie für die Market Basket-Analyse, fügen jedoch eine Spalte mit dem `sequence`-Bezeichner hinzu.</span><span class="sxs-lookup"><span data-stu-id="648a4-104">You will use the same data source view that you used for the market basket analysis, but you will add a column that contains the `sequence` identifier.</span></span> <span data-ttu-id="648a4-105">In diesem Szenario bezeichnet "Sequenz" die Reihenfolge, in der die Elemente vom Kunden im Warenkorb abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="648a4-105">In this scenario, the sequence means the order in which the customer added items to the shopping basket.</span></span>  
  
 <span data-ttu-id="648a4-106">Darüber hinaus fügen Sie einige Spalten hinzu, die in einem der Modelle zum Gruppieren von Kunden anhand demografischer Daten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="648a4-106">You will also add some columns that are used in one of the models to group customers by demographics.</span></span>  
  
### <a name="to-create-a-sequence-clustering-structure-and-model"></a><span data-ttu-id="648a4-107">So erstellen Sie eine Sequenzclusterstruktur und ein Sequenzclustermodell</span><span class="sxs-lookup"><span data-stu-id="648a4-107">To create a sequence clustering structure and model</span></span>  
  
1.  <span data-ttu-id="648a4-108">Klicken Sie in Projektmappen-Explorer in mit der [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] rechten Maustaste auf **Mining Strukturen** , und wählen Sie **neue Mining Struktur**aus.</span><span class="sxs-lookup"><span data-stu-id="648a4-108">In Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], right-click **Mining Structures** and select **New Mining Structure**.</span></span>  
  
2.  <span data-ttu-id="648a4-109">Klicken Sie auf der Seite **Willkommen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="648a4-109">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="648a4-110">Überprüfen Sie auf der Seite **Definitions Methode auswählen** , ob **aus vorhandener relationaler Datenbank oder Data Warehouse** ausgewählt ist, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="648a4-110">On the **Select the Definition Method** page, verify that **From existing relational database or data warehouse** is selected, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="648a4-111">Vergewissern Sie sich auf der Seite **Data Mining-Struktur erstellen** , dass die Option **Mining Struktur mit einem Mining Modell erstellen** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="648a4-111">On the **Create the Data Mining Structure** page, verify that the option **Create mining structure with a mining model** is selected.</span></span> <span data-ttu-id="648a4-112">Klicken Sie anschließend auf die Dropdown Liste für die Option, **welche Data Mining Technik Sie verwenden möchten?**, und wählen Sie **Microsoft Sequence Clustering**aus.</span><span class="sxs-lookup"><span data-stu-id="648a4-112">Next, click the dropdown list for the option, **Which data mining technique do you want to use?**, and select **Microsoft Sequence Clustering**.</span></span> <span data-ttu-id="648a4-113">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="648a4-113">Click **Next**.</span></span>  
  
     <span data-ttu-id="648a4-114">Die Seite **Datenquellen Sicht auswählen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="648a4-114">The **Select Data Source View** page appears.</span></span> <span data-ttu-id="648a4-115">Wählen Sie unter **Verfügbare Datenquellen Sichten**die Option aus `Orders` .</span><span class="sxs-lookup"><span data-stu-id="648a4-115">Under **Available data source views**, select `Orders`.</span></span>  
  
     <span data-ttu-id="648a4-116">Orders ist die gleiche Datenquellensicht, die Sie auch für das Market Basket-Szenario verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="648a4-116">Orders is the same data source view that you used for the market basket scenario.</span></span> <span data-ttu-id="648a4-117">Wenn Sie diese Datenquellen Sicht nicht erstellt haben, finden Sie weitere Informationen unter [Hinzufügen einer Datenquellen Sicht mit Tabellen &#40;Data Mining ](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md)-Lernprogramm für fortgeschrittene&#41;.</span><span class="sxs-lookup"><span data-stu-id="648a4-117">If you have not created this data source view, see [Adding a Data Source View with Nested Tables &#40;Intermediate Data Mining Tutorial&#41;](../../2014/tutorials/adding-a-data-source-view-with-nested-tables-intermediate-data-mining-tutorial.md).</span></span>  
  
5.  <span data-ttu-id="648a4-118">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="648a4-118">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="648a4-119">Aktivieren Sie auf der Seite **Tabellentypen angeben** neben der Tabelle **vassoctarqorders** das Kontrollkästchen **Fall** , und aktivieren Sie das Kontrollkästchen **Nested** neben der Tabelle **vassoctarqlineitems** .</span><span class="sxs-lookup"><span data-stu-id="648a4-119">On the **Specify Table Types** page, select the **Case** check box next to the **vAssocSeqOrders** table, and select the **Nested** check box next to the **vAssocSeqLineItems** table.</span></span> <span data-ttu-id="648a4-120">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="648a4-120">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="648a4-121">Wenn ein Fehler auftritt, wenn Sie die **Kontrollkästchen für** die Groß-/Kleinschreibung oder die Option aktivieren, ist der Join in der Datenquellen Sicht möglicherweise nicht korrekt. **Case**</span><span class="sxs-lookup"><span data-stu-id="648a4-121">If an error occurs when you select the **Case** or **Nested** check boxes, it may be that the join in the data source view is not correct.</span></span> <span data-ttu-id="648a4-122">Die geschachtelte Table **vassocot qlineitems**muss mit der Fall Tabelle **vassocc-qorders** durch einen n:1-Join verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="648a4-122">The nested table, **vAssocSeqLineItems**, must be connected to the case table, **vAssocSeqOrders,** by a many-to-one join.</span></span> <span data-ttu-id="648a4-123">Sie können die Beziehung bearbeiten, indem Sie mit der rechten Maustaste auf die Joinlinie klicken und dann die Richtung des Joins umkehren.</span><span class="sxs-lookup"><span data-stu-id="648a4-123">You can edit the relationship by right-clicking on the join line and then reversing the direction of the join.</span></span> <span data-ttu-id="648a4-124">Weitere Informationen finden Sie unter [Dialog Feld "Beziehung erstellen oder bearbeiten" &#40;Analysis Services-mehrdimensionalen Daten&#41;](../../2014/analysis-services/create-or-edit-relationship-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="648a4-124">For more information, see [Create or Edit Relationship Dialog Box &#40;Analysis Services - Multidimensional Data&#41;](../../2014/analysis-services/create-or-edit-relationship-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
7.  <span data-ttu-id="648a4-125">Wählen Sie auf der Seite **Trainingsdaten angeben** die Spalten aus, die im Modell verwendet werden sollen, indem Sie wie folgt ein Kontrollkästchen aktivieren:</span><span class="sxs-lookup"><span data-stu-id="648a4-125">On the **Specify the Training Data** page, choose the columns for use in the model by selecting a check box as follows:</span></span>  
  
    -   <span data-ttu-id="648a4-126">**IncomeGroup** Aktivieren Sie das Kontrollkästchen **Eingabe** .</span><span class="sxs-lookup"><span data-stu-id="648a4-126">**IncomeGroup** Select the **Input** check box.</span></span>  
  
         <span data-ttu-id="648a4-127">Diese Spalte enthält interessante Informationen über die Kunden, die Sie für das Clustering verwenden können.</span><span class="sxs-lookup"><span data-stu-id="648a4-127">This column contains interesting information about the customers that you can use for clustering.</span></span> <span data-ttu-id="648a4-128">Eine Verwendung findet nur im ersten Modell, nicht jedoch im zweiten Modell statt.</span><span class="sxs-lookup"><span data-stu-id="648a4-128">You will use it in the first model and then ignore it in the second model.</span></span>  
  
    -   <span data-ttu-id="648a4-129">**OrderNumber** Aktivieren Sie das `Key` Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="648a4-129">**OrderNumber** Select the `Key` check box.</span></span>  
  
         <span data-ttu-id="648a4-130">Dieses Feld wird als Bezeichner oder `Key` für die Falltabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="648a4-130">This field will be used as the identifier for the case table, or `Key`.</span></span> <span data-ttu-id="648a4-131">Das Schlüsselfeld der Falltabelle sollte nicht als Eingabe verwendet werden, da der Schlüssel eindeutige Werte enthält, die nicht nützlich für das Clustering sind.</span><span class="sxs-lookup"><span data-stu-id="648a4-131">In general, you should never use the key field of the case table as an input, because the key contains unique values that are not useful for clustering.</span></span>  
  
    -   <span data-ttu-id="648a4-132">**Region** Aktivieren Sie das Kontrollkästchen **Eingabe** .</span><span class="sxs-lookup"><span data-stu-id="648a4-132">**Region** Select the **Input** check box.</span></span>  
  
         <span data-ttu-id="648a4-133">Diese Spalte enthält interessante Informationen über die Kunden, die Sie für das Clustering verwenden können.</span><span class="sxs-lookup"><span data-stu-id="648a4-133">This column contains interesting information about the customers that you can use for clustering.</span></span> <span data-ttu-id="648a4-134">Eine Verwendung findet nur im ersten Modell, nicht jedoch im zweiten Modell statt.</span><span class="sxs-lookup"><span data-stu-id="648a4-134">You will use it in the first model and then ignore it in the second model.</span></span>  
  
    -   <span data-ttu-id="648a4-135">**LineNumber** Aktivieren Sie `Key` die **Input** Kontrollkästchen und.</span><span class="sxs-lookup"><span data-stu-id="648a4-135">**LineNumber** Select the `Key` and **Input** check boxes.</span></span>  
  
         <span data-ttu-id="648a4-136">Das Feld " **LineNumber** " wird als Bezeichner für die geänderte Tabelle oder verwendet `Sequence Key` .</span><span class="sxs-lookup"><span data-stu-id="648a4-136">The **LineNumber** field will be used as the identifier for the nested table, or `Sequence Key`.</span></span> <span data-ttu-id="648a4-137">Der Schlüssel für eine geschachtelte Tabelle muss immer für die Eingabe verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="648a4-137">The key for a nested table must always be used for input.</span></span>  
  
    -   <span data-ttu-id="648a4-138">**Modell** Aktivieren Sie die Kontrollkästchen **Eingabe** und **vorhersagbar** .</span><span class="sxs-lookup"><span data-stu-id="648a4-138">**Model** Select the **Input** and **Predictable** check boxes.</span></span>  
  
     <span data-ttu-id="648a4-139">Überprüfen Sie, ob die Auswahl richtig ist, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="648a4-139">Verify that the selections are correct, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="648a4-140">Überprüfen Sie auf der Seite **Inhalt und Datentyp der Spalten angeben** , ob das Raster die Spalten, Inhaltstypen und Datentypen enthält, die in der folgenden Tabelle angezeigt werden, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="648a4-140">On the **Specify Columns' Content and Data Type** page, verify that the grid contains the columns, content types, and data types shown in the following table, and then click **Next**.</span></span>  
  
    |<span data-ttu-id="648a4-141">Tabellen/Spalten</span><span class="sxs-lookup"><span data-stu-id="648a4-141">Tables/Columns</span></span>|<span data-ttu-id="648a4-142">Inhaltstyp</span><span class="sxs-lookup"><span data-stu-id="648a4-142">Content Type</span></span>|<span data-ttu-id="648a4-143">Datentyp</span><span class="sxs-lookup"><span data-stu-id="648a4-143">Data Type</span></span>|  
    |---------------------|------------------|---------------|  
    |<span data-ttu-id="648a4-144">IncomeGroup</span><span class="sxs-lookup"><span data-stu-id="648a4-144">IncomeGroup</span></span>|<span data-ttu-id="648a4-145">Discrete</span><span class="sxs-lookup"><span data-stu-id="648a4-145">Discrete</span></span>|<span data-ttu-id="648a4-146">Text</span><span class="sxs-lookup"><span data-stu-id="648a4-146">Text</span></span>|  
    |<span data-ttu-id="648a4-147">OrderNumber</span><span class="sxs-lookup"><span data-stu-id="648a4-147">OrderNumber</span></span>|<span data-ttu-id="648a4-148">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="648a4-148">Key</span></span>|<span data-ttu-id="648a4-149">Text</span><span class="sxs-lookup"><span data-stu-id="648a4-149">Text</span></span>|  
    |<span data-ttu-id="648a4-150">Region</span><span class="sxs-lookup"><span data-stu-id="648a4-150">Region</span></span>|<span data-ttu-id="648a4-151">Discrete</span><span class="sxs-lookup"><span data-stu-id="648a4-151">Discrete</span></span>|<span data-ttu-id="648a4-152">Text</span><span class="sxs-lookup"><span data-stu-id="648a4-152">Text</span></span>|  
    |<span data-ttu-id="648a4-153">vAssocSeqLineItems</span><span class="sxs-lookup"><span data-stu-id="648a4-153">vAssocSeqLineItems</span></span>|||  
    |<span data-ttu-id="648a4-154">Zeilennummer</span><span class="sxs-lookup"><span data-stu-id="648a4-154">Line Number</span></span>|<span data-ttu-id="648a4-155">Key Sequence</span><span class="sxs-lookup"><span data-stu-id="648a4-155">Key Sequence</span></span>|<span data-ttu-id="648a4-156">Long</span><span class="sxs-lookup"><span data-stu-id="648a4-156">Long</span></span>|  
    |<span data-ttu-id="648a4-157">Modell</span><span class="sxs-lookup"><span data-stu-id="648a4-157">Model</span></span>|<span data-ttu-id="648a4-158">Discrete</span><span class="sxs-lookup"><span data-stu-id="648a4-158">Discrete</span></span>|<span data-ttu-id="648a4-159">Text</span><span class="sxs-lookup"><span data-stu-id="648a4-159">Text</span></span>|  
  
9. <span data-ttu-id="648a4-160">Ändern Sie auf der Seite **Testsatz erstellen** den **Prozentsatz der zu testenden Daten** auf 20, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="648a4-160">On the **Create Testing Set** page, change the **Percentage of data for testing** to 20, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="648a4-161">Geben Sie auf der Seite **Assistenten abschließen** für **Mining Struktur Name den Namen**ein `Sequence Clustering with Region` .</span><span class="sxs-lookup"><span data-stu-id="648a4-161">On the **Completing the Wizard** page, for the **Mining structure name**, type `Sequence Clustering with Region`.</span></span>  
  
11. <span data-ttu-id="648a4-162">Geben Sie für **Mining Modellname den Namen**ein `Sequence Clustering with Region` .</span><span class="sxs-lookup"><span data-stu-id="648a4-162">For the **Mining model name**, type `Sequence Clustering with Region`.</span></span>  
  
12. <span data-ttu-id="648a4-163">Aktivieren Sie das Kontrollkästchen **Drillthrough zulassen** , und klicken Sie dann auf **Fertig**stellen.</span><span class="sxs-lookup"><span data-stu-id="648a4-163">Check the **Allow drill through** box, and then click **Finish**.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="648a4-164">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="648a4-164">Next Task in Lesson</span></span>  
 [<span data-ttu-id="648a4-165">Verarbeiten des Sequenzclustermodells</span><span class="sxs-lookup"><span data-stu-id="648a4-165">Processing the Sequence Clustering Model</span></span>](../../2014/tutorials/processing-the-sequence-clustering-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="648a4-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="648a4-166">See Also</span></span>  
 <span data-ttu-id="648a4-167">[Data Mining-Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span><span class="sxs-lookup"><span data-stu-id="648a4-167">[Data Mining Designer](../../2014/analysis-services/data-mining/data-mining-designer.md) </span></span>  
 [<span data-ttu-id="648a4-168">Microsoft Sequence Clustering-Algorithmus</span><span class="sxs-lookup"><span data-stu-id="648a4-168">Microsoft Sequence Clustering Algorithm</span></span>](../../2014/analysis-services/data-mining/microsoft-sequence-clustering-algorithm.md)  
  
  
