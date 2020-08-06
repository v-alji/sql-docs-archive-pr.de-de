---
title: Ändern der Product-Dimension | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 8e3ffecd-7f40-41a8-8735-bc9858a310cb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 04c0a778a73371dada92c9ff207a17366a2fbc7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619434"
---
# <a name="modifying-the-product-dimension"></a><span data-ttu-id="cb4f5-102">Ändern der Product-Dimension</span><span class="sxs-lookup"><span data-stu-id="cb4f5-102">Modifying the Product Dimension</span></span>
  <span data-ttu-id="cb4f5-103">In den Aufgaben in diesem Thema verwenden Sie eine benannte Berechnung, um aussagekräftigere Namen für Produktlinien zur Verfügung zu stellen, definieren eine Hierarchie in der Product-Dimension, und geben den (All) -Elementnamen für die Hierarchie an.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-103">In the tasks in this topic, you use a named calculation to provide more descriptive names for the product lines, define a hierarchy in the Product dimension, and specify the (All) member name for the hierarchy.</span></span> <span data-ttu-id="cb4f5-104">Außerdem gruppieren Sie Attribute in Anzeigeordner.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-104">You also group attributes into display folders.</span></span>  
  
## <a name="adding-a-named-calculation"></a><span data-ttu-id="cb4f5-105">Hinzufügen einer benannten Berechnung</span><span class="sxs-lookup"><span data-stu-id="cb4f5-105">Adding a Named Calculation</span></span>  
 <span data-ttu-id="cb4f5-106">Sie können einer Tabelle in einer Datenquellensicht eine benannte Berechnung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-106">You can add a named calculation to a table in a data source view.</span></span> <span data-ttu-id="cb4f5-107">In der folgenden Aufgabe erstellen Sie eine benannte Berechnung, die den vollständigen Produktliniennamen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-107">In the following task, you create a named calculation that displays the full product line name.</span></span>  
  
#### <a name="to-add-a-named-calculation"></a><span data-ttu-id="cb4f5-108">So fügen Sie eine benannte Berechnung hinzu</span><span class="sxs-lookup"><span data-stu-id="cb4f5-108">To add a named calculation</span></span>  
  
1.  <span data-ttu-id="cb4f5-109">Um die **Adventure Works DW 2012** -Datenquellensicht zu öffnen, doppelklicken Sie im Projektmappen-Explorer im Ordner **Datenquellensichten** auf **Adventure Works DW 2012** .</span><span class="sxs-lookup"><span data-stu-id="cb4f5-109">To open the **Adventure Works DW 2012** data source view, double-click **Adventure Works DW 2012** in the **Data Source Views** folder in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="cb4f5-110">Klicken Sie unten im Diagrammbereich mit der rechten Maustaste auf die Tabellenüberschrift **Product** . Klicken Sie anschließend auf **Neue benannte Berechnung**.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-110">In the bottom of the diagram pane, right-click the **Product** table header, and then click **New Named Calculation**.</span></span>  
  
3.  <span data-ttu-id="cb4f5-111">Geben Sie im Dialogfeld **benannte Berechnung erstellen** `ProductLineName` im Feld **Spaltenname** ein.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-111">In the **Create Named Calculation** dialog box, type `ProductLineName` in the **Column name** box.</span></span>  
  
4.  <span data-ttu-id="cb4f5-112">Geben Sie in das Feld **Ausdruck** die folgende **CASE** -Anweisung ein (Sie können sie auch kopieren und einfügen):</span><span class="sxs-lookup"><span data-stu-id="cb4f5-112">In the **Expression** box, type or copy and paste the following **CASE** statement:</span></span>  
  
    ```  
    CASE ProductLine  
       WHEN 'M' THEN 'Mountain'  
       WHEN 'R' THEN 'Road'  
       WHEN 'S' THEN 'Accessory'  
       WHEN 'T' THEN 'Touring'  
       ELSE 'Components'  
    END  
    ```  
  
     <span data-ttu-id="cb4f5-113">Diese **CASE** -Anweisung erstellt benutzerfreundliche Namen für jede Produktlinie im Cube.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-113">This **CASE** statement creates user-friendly names for each product line in the cube.</span></span>  
  
5.  <span data-ttu-id="cb4f5-114">Klicken Sie auf **OK** , um die `ProductLineName` benannte Berechnung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-114">Click **OK** to create the `ProductLineName` named calculation.</span></span> <span data-ttu-id="cb4f5-115">Sie müssen möglicherweise einen Moment warten.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-115">You might need to wait.</span></span>  
  
6.  <span data-ttu-id="cb4f5-116">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="cb4f5-116">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="modifying-the-namecolumn-property-of-an-attribute"></a><span data-ttu-id="cb4f5-117">Ändern der NameColumn-Eigenschaft eines Attributs</span><span class="sxs-lookup"><span data-stu-id="cb4f5-117">Modifying the NameColumn Property of an Attribute</span></span>  
  
#### <a name="to-modify-the-namecolumn-property-value-of-an-attribute"></a><span data-ttu-id="cb4f5-118">So ändern Sie den Wert der NameColumns-Eigenschaft eines Attributs</span><span class="sxs-lookup"><span data-stu-id="cb4f5-118">To modify the NameColumn property value of an attribute</span></span>  
  
1.  <span data-ttu-id="cb4f5-119">Wechseln Sie zum Dimensions-Designer für die Product-Dimension.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-119">Switch to Dimension Designer for the Product dimension.</span></span> <span data-ttu-id="cb4f5-120">Doppelklicken Sie dazu auf die **Product** -Dimension im **Dimensionen** -Knoten des Projektmappen-Explorers.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-120">To do this, double-click the **Product** dimension in the **Dimensions** node of Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="cb4f5-121">Wählen Sie im Bereich **Attribute** der Registerkarte **Dimensionsstruktur** die Option **Product Line**aus.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-121">In the **Attributes** pane of the **Dimension Structure** tab, select **Product Line**.</span></span>  
  
3.  <span data-ttu-id="cb4f5-122">Klicken Sie im Eigenschaftenfenster auf der rechten Seite des Bildschirms unten im Fenster auf das Eigenschafts Feld **namecolumzun** , und klicken Sie dann auf die Schaltfläche zum Durchsuchen (**..**.), um das Dialogfeld **Namensspalte** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-122">In the Properties window on the right side of the screen, click the **NameColumn** property field at the bottom of the window, and then click the browse (**...**) button to open the **Name Column** dialog box.</span></span> <span data-ttu-id="cb4f5-123">(Sie müssen ggf. auf die Registerkarte **Eigenschaften** auf der rechten Seite vom Bildschirm klicken, um das Eigenschaftenfenster zu öffnen).</span><span class="sxs-lookup"><span data-stu-id="cb4f5-123">(You might need to click the **Properties** tab on the right side of the screen to open the Properties window.</span></span>  
  
4.  <span data-ttu-id="cb4f5-124">Wählen Sie `ProductLineName` unten in der Liste **Quell Spalte** die Option aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-124">Select `ProductLineName` at the bottom of the **Source column** list, and then click **OK**.</span></span>  
  
     <span data-ttu-id="cb4f5-125">Das Feld „NameColumn“ enthält jetzt den Text **Product.ProductLineName (WChar)**.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-125">The NameColumn field now contains the text, **Product.ProductLineName (WChar)**.</span></span> <span data-ttu-id="cb4f5-126">Die Elemente der Attributhierarchie **Product Line** zeigen nun den vollständigen Namen der Produktlinie anstelle eines abgekürzten Produktliniennamens an.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-126">The members of the **Product Line** attribute hierarchy now display the full name of the product line instead of an abbreviated product line name.</span></span>  
  
5.  <span data-ttu-id="cb4f5-127">Wählen Sie im Bereich **Attribute** der Registerkarte **Dimensionsstruktur** die Option **Product Key**aus.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-127">In the **Attributes** pane of the **Dimension Structure** tab, select **Product Key**.</span></span>  
  
6.  <span data-ttu-id="cb4f5-128">Klicken Sie im Eigenschaftenfenster auf das Eigenschafts Feld **namecolumzun** , und klicken Sie dann auf die Schaltfläche mit den Auslassungs Punkten (**...**), um das Dialogfeld **Namensspalte** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-128">In the Properties window, click the **NameColumn** property field, and then click the ellipsis browse (**...**) button to open the **Name Column** dialog box.</span></span>  
  
7.  <span data-ttu-id="cb4f5-129">Wählen Sie **EnglishProductName** in der Liste **Quellspalte** aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-129">Select **EnglishProductName** in the **Source column** list, and then click **OK**.</span></span>  
  
     <span data-ttu-id="cb4f5-130">Das Feld "NameColumn" enthält jetzt den Text **Product.EnglishProductName (WChar)**.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-130">The NameColumn field now contains the text, **Product.EnglishProductName (WChar)**.</span></span>  
  
8.  <span data-ttu-id="cb4f5-131">Scrollen Sie im Eigenschaftenfenster nach oben, klicken Sie auf das Eigenschafts Feld **Name** , und geben Sie dann ein `Product Name` .</span><span class="sxs-lookup"><span data-stu-id="cb4f5-131">In the Properties window, scroll up, click the **Name** property field, and then type `Product Name`.</span></span>  
  
## <a name="creating-a-hierarchy"></a><span data-ttu-id="cb4f5-132">Erstellen einer Hierarchie</span><span class="sxs-lookup"><span data-stu-id="cb4f5-132">Creating a Hierarchy</span></span>  
  
#### <a name="to-create-a-hierarchy"></a><span data-ttu-id="cb4f5-133">So erstellen Sie eine Hierarchie</span><span class="sxs-lookup"><span data-stu-id="cb4f5-133">To create a hierarchy</span></span>  
  
1.  <span data-ttu-id="cb4f5-134">Ziehen Sie das **Product Line** -Attribut vom Bereich **Attribute** in den Bereich **Hierarchien** .</span><span class="sxs-lookup"><span data-stu-id="cb4f5-134">Drag the **Product Line** attribute from the **Attributes** pane into the **Hierarchies** pane.</span></span>  
  
2.  <span data-ttu-id="cb4f5-135">Ziehen Sie das **Model Name** -Attribut aus dem **Attribute** -Bereich in die Zelle **\<new level>** des Bereichs **Hierarchien** unterhalb der **Product Line** -Ebene.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-135">Drag the **Model Name** attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Product Line** level.</span></span>  
  
3.  <span data-ttu-id="cb4f5-136">Ziehen Sie das- `Product Name` Attribut aus dem Bereich **Attribute** in die Zelle des Bereichs **\<new level>** **Hierarchien** unterhalb der **Model Name** -Ebene.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-136">Drag the `Product Name` attribute from the **Attributes** pane into the **\<new level>** cell in the **Hierarchies** pane, underneath the **Model Name** level.</span></span> <span data-ttu-id="cb4f5-137">(Sie haben im vorherigen Abschnitt Product Key in Product Name umbenannt.)</span><span class="sxs-lookup"><span data-stu-id="cb4f5-137">(You renamed Product Key to Product Name in the previous section.)</span></span>  
  
4.  <span data-ttu-id="cb4f5-138">Klicken Sie im Bereich **Hierarchien** der Registerkarte **Dimensions Struktur** mit der rechten Maustaste auf die Titelleiste der **Hierarchie** Hierarchie, klicken Sie auf **Umbenennen**, und geben Sie dann ein `Product Model Lines` .</span><span class="sxs-lookup"><span data-stu-id="cb4f5-138">In the **Hierarchies** pane of the **Dimension Structure** tab, right-click the title bar of the **Hierarchy** hierarchy, click **Rename**, and then type `Product Model Lines`.</span></span>  
  
     <span data-ttu-id="cb4f5-139">Der Name der Hierarchie lautet jetzt `Product Model Lines` .</span><span class="sxs-lookup"><span data-stu-id="cb4f5-139">The name of the hierarchy is now `Product Model Lines`.</span></span>  
  
5.  <span data-ttu-id="cb4f5-140">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="cb4f5-140">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="specifying-folder-names-and-all-member-names"></a><span data-ttu-id="cb4f5-141">Angeben von Ordnernamen und Namen für alle Elemente</span><span class="sxs-lookup"><span data-stu-id="cb4f5-141">Specifying Folder Names and All Member Names</span></span>  
  
#### <a name="to-specify-the-folder-and-member-names"></a><span data-ttu-id="cb4f5-142">So geben Sie die Ordner- und Elementnamen an</span><span class="sxs-lookup"><span data-stu-id="cb4f5-142">To specify the folder and member names</span></span>  
  
1.  <span data-ttu-id="cb4f5-143">Wählen Sie im Bereich **Attribute** die folgenden Attribute, indem Sie beim Klicken die STRG-Taste gedrückt halten:</span><span class="sxs-lookup"><span data-stu-id="cb4f5-143">In the **Attributes** pane, select the following attributes by holding down the CTRL key while clicking each of them:</span></span>  
  
    -   <span data-ttu-id="cb4f5-144">**Klasse**</span><span class="sxs-lookup"><span data-stu-id="cb4f5-144">**Class**</span></span>  
  
    -   <span data-ttu-id="cb4f5-145">**Farbe**</span><span class="sxs-lookup"><span data-stu-id="cb4f5-145">**Color**</span></span>  
  
    -   <span data-ttu-id="cb4f5-146">**Zu Produktionstage**</span><span class="sxs-lookup"><span data-stu-id="cb4f5-146">**Days To Manufacture**</span></span>  
  
    -   <span data-ttu-id="cb4f5-147">**Reorder Point**</span><span class="sxs-lookup"><span data-stu-id="cb4f5-147">**Reorder Point**</span></span>  
  
    -   <span data-ttu-id="cb4f5-148">**Safety Stock Level**</span><span class="sxs-lookup"><span data-stu-id="cb4f5-148">**Safety Stock Level**</span></span>  
  
    -   <span data-ttu-id="cb4f5-149">**Größe**</span><span class="sxs-lookup"><span data-stu-id="cb4f5-149">**Size**</span></span>  
  
    -   <span data-ttu-id="cb4f5-150">**Size Range**</span><span class="sxs-lookup"><span data-stu-id="cb4f5-150">**Size Range**</span></span>  
  
    -   <span data-ttu-id="cb4f5-151">**style**</span><span class="sxs-lookup"><span data-stu-id="cb4f5-151">**Style**</span></span>  
  
    -   <span data-ttu-id="cb4f5-152">**Weight**</span><span class="sxs-lookup"><span data-stu-id="cb4f5-152">**Weight**</span></span>  
  
2.  <span data-ttu-id="cb4f5-153">Geben Sie im Eigenschaftenfenster **AttributeHierarchyDisplayFolder** -Eigenschafts Feld ein `Stocking` .</span><span class="sxs-lookup"><span data-stu-id="cb4f5-153">In the **AttributeHierarchyDisplayFolder** property field in the Properties window, type `Stocking`.</span></span>  
  
     <span data-ttu-id="cb4f5-154">Sie haben diese Attribute jetzt in einen einzigen Anzeigeordner gruppiert.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-154">You have now grouped these attributes into a single display folder.</span></span>  
  
3.  <span data-ttu-id="cb4f5-155">Wählen Sie im Bereich **Attribute** die folgenden Attribute aus:</span><span class="sxs-lookup"><span data-stu-id="cb4f5-155">In the **Attributes** pane, select the following attributes:</span></span>  
  
    -   <span data-ttu-id="cb4f5-156">**Dealer Price**</span><span class="sxs-lookup"><span data-stu-id="cb4f5-156">**Dealer Price**</span></span>  
  
    -   <span data-ttu-id="cb4f5-157">**List Price**</span><span class="sxs-lookup"><span data-stu-id="cb4f5-157">**List Price**</span></span>  
  
    -   <span data-ttu-id="cb4f5-158">**Standard Cost**</span><span class="sxs-lookup"><span data-stu-id="cb4f5-158">**Standard Cost**</span></span>  
  
4.  <span data-ttu-id="cb4f5-159">Geben Sie in der **AttributeHierarchyDisplayFolder** -Eigenschafts Zelle im Eigenschaftenfenster ein `Financial` .</span><span class="sxs-lookup"><span data-stu-id="cb4f5-159">In the **AttributeHierarchyDisplayFolder** property cell in the Properties window, type `Financial`.</span></span>  
  
     <span data-ttu-id="cb4f5-160">Sie haben diese Attribute jetzt in einen zweiten Anzeigeordner gruppiert.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-160">You have now grouped these attributes into a second display folder.</span></span>  
  
5.  <span data-ttu-id="cb4f5-161">Wählen Sie im Bereich **Attribute** die folgenden Attribute aus:</span><span class="sxs-lookup"><span data-stu-id="cb4f5-161">In the **Attributes** pane, select the following attributes:</span></span>  
  
    -   <span data-ttu-id="cb4f5-162">**Enddatum**</span><span class="sxs-lookup"><span data-stu-id="cb4f5-162">**End Date**</span></span>  
  
    -   <span data-ttu-id="cb4f5-163">**Startdatum**</span><span class="sxs-lookup"><span data-stu-id="cb4f5-163">**Start Date**</span></span>  
  
    -   <span data-ttu-id="cb4f5-164">**Status**</span><span class="sxs-lookup"><span data-stu-id="cb4f5-164">**Status**</span></span>  
  
6.  <span data-ttu-id="cb4f5-165">Geben Sie in der **AttributeHierarchyDisplayFolder** -Eigenschafts Zelle im Eigenschaftenfenster ein `History` .</span><span class="sxs-lookup"><span data-stu-id="cb4f5-165">In the **AttributeHierarchyDisplayFolder** property cell in the Properties window, type `History`.</span></span>  
  
     <span data-ttu-id="cb4f5-166">Sie haben diese Attribute jetzt in einen dritten Anzeigeordner gruppiert.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-166">You have now grouped these attributes into a third display folder.</span></span>  
  
7.  <span data-ttu-id="cb4f5-167">Wählen Sie die `Product Model Lines` Hierarchie im Bereich **Hierarchien** aus, und ändern Sie dann die **allmembership Name** -Eigenschaft in der Eigenschaftenfenster auf `All Products` .</span><span class="sxs-lookup"><span data-stu-id="cb4f5-167">Select the `Product Model Lines` hierarchy in the **Hierarchies** pane, and then change the **AllMemberName** property in the Properties window to `All Products`.</span></span>  
  
8.  <span data-ttu-id="cb4f5-168">Klicken Sie im Bereich **Hierarchien** auf einen geöffneten Bereich, und ändern Sie dann die **attributeallmembership Name** -Eigenschaft am oberen Rand des Eigenschaftenfenster in `All Products` .</span><span class="sxs-lookup"><span data-stu-id="cb4f5-168">Click an open area of the **Hierarchies** pane, and then change the **AttributeAllMemberName** property at the top of the Properties window to `All Products`.</span></span>  
  
     <span data-ttu-id="cb4f5-169">Durch das Anklicken eines offenen Bereichs können Sie Eigenschaften der Produktdimension selbst ändern.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-169">Clicking an open area lets you modify properties of the Product dimension itself.</span></span> <span data-ttu-id="cb4f5-170">Sie können auch auf **Product** am oberen Rand der Attributliste im Bereich **Attribute** klicken.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-170">You could also click **Product** at the top of the attributes list in the **Attributes** pane.</span></span>  
  
9. <span data-ttu-id="cb4f5-171">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="cb4f5-171">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="defining-attribute-relationships"></a><span data-ttu-id="cb4f5-172">Definieren von Attributbeziehungen</span><span class="sxs-lookup"><span data-stu-id="cb4f5-172">Defining Attribute Relationships</span></span>  
 <span data-ttu-id="cb4f5-173">Sofern die zugrunde liegenden Daten dies unterstützen, sollten Sie auch Attributbeziehungen zwischen Attributen definieren.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-173">If the underlying data supports it, you should define attribute relationships between attributes.</span></span> <span data-ttu-id="cb4f5-174">Durch Definieren von Attributbeziehungen wird die Dimensions-, Partitions- und Abfrageverarbeitung beschleunigt.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-174">Defining attribute relationships speeds up dimension, partition, and query processing.</span></span> <span data-ttu-id="cb4f5-175">Weitere Informationen finden Sie unter [Definieren von Attributbeziehungen](multidimensional-models/attribute-relationships-define.md) und [Attributbeziehungen](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="cb4f5-175">For more information, see [Define Attribute Relationships](multidimensional-models/attribute-relationships-define.md) and [Attribute Relationships](multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
#### <a name="to-define-attribute-relationships"></a><span data-ttu-id="cb4f5-176">So definieren Sie Attributbeziehungen</span><span class="sxs-lookup"><span data-stu-id="cb4f5-176">To define attribute relationships</span></span>  
  
1.  <span data-ttu-id="cb4f5-177">Klicken Sie im **Dimensions-Designer** für die Product-Dimension auf die Registerkarte **Attributbeziehungen** .</span><span class="sxs-lookup"><span data-stu-id="cb4f5-177">In the **Dimension Designer** for the Product dimension, click the **Attribute Relationships** tab.</span></span>  
  
2.  <span data-ttu-id="cb4f5-178">Klicken Sie im Diagramm mit der rechten Maustaste auf das **Model Name** -Attribut und anschließend auf **Neue Attributbeziehung**.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-178">In the diagram, right-click the **Model Name** attribute, and then click **New Attribute Relationship**.</span></span>  
  
3.  <span data-ttu-id="cb4f5-179">Im Dialogfeld **Attributbeziehung erstellen** lautet das **Quellattribut\*\*\*\*Model Name**.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-179">In the **Create Attribute Relationship** dialog box, the **Source Attribute** is **Model Name**.</span></span> <span data-ttu-id="cb4f5-180">Legen Sie für **Verknüpftes Attribut** die Einstellung **Produktgruppe**fest.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-180">Set the **Related Attribute** to **Product Line**.</span></span>  
  
     <span data-ttu-id="cb4f5-181">Belassen Sie in der Liste **Beziehungstyp** den Beziehungstyp auf **Flexibel** , da sich Beziehungen zwischen den Elementen im Laufe der Zeit ändern können.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-181">In the **Relationship type** list, leave the relationship type set to **Flexible** because relationships between the members might change over time.</span></span> <span data-ttu-id="cb4f5-182">So könnte ein Produktmodell beispielsweise in eine andere Produktlinie verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-182">For example, a product model might eventually be moved to a different product line.</span></span>  
  
4.  <span data-ttu-id="cb4f5-183">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-183">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="cb4f5-184">Klicken Sie im Menü **File** (Datei) auf **Save All** (Alles speichern).</span><span class="sxs-lookup"><span data-stu-id="cb4f5-184">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="reviewing-product-dimension-changes"></a><span data-ttu-id="cb4f5-185">Überprüfen von Produktdimensionsänderungen</span><span class="sxs-lookup"><span data-stu-id="cb4f5-185">Reviewing Product Dimension Changes</span></span>  
  
#### <a name="to-review-the-product-dimension-changes"></a><span data-ttu-id="cb4f5-186">So überprüfen Sie die Produktdimensionsänderungen</span><span class="sxs-lookup"><span data-stu-id="cb4f5-186">To review the Product dimension changes</span></span>  
  
1.  <span data-ttu-id="cb4f5-187">Klicken Sie im Menü **Erstellen** von [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]auf **Analysis Services Tutorial bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-187">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="cb4f5-188">Nachdem die Meldung **Bereitstellung erfolgreich abgeschlossen** angezeigt wird, klicken Sie auf die Registerkarte **Browser** im **Dimensions-Designer** für die **Product** -Dimension und anschließend auf der Symbolleiste auf die Schaltfläche zum Wiederherstellen der Verbindung.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-188">After you have received the **Deployment Completed Successfully** message, click the **Browser** tab of **Dimension Designer** for the **Product** dimension, and then click the Reconnect button on the toolbar of the designer.</span></span>  
  
3.  <span data-ttu-id="cb4f5-189">Vergewissern Sie sich, dass `Product Model Lines` in der Liste **Hierarchie** ausgewählt ist, und erweitern Sie dann `All Products` .</span><span class="sxs-lookup"><span data-stu-id="cb4f5-189">Verify that `Product Model Lines` is selected in the **Hierarchy** list, and then expand `All Products`.</span></span>  
  
     <span data-ttu-id="cb4f5-190">Beachten Sie, dass der Name des Elements **alle** als angezeigt wird `All Products` .</span><span class="sxs-lookup"><span data-stu-id="cb4f5-190">Notice that the name of the **All** member appears as `All Products`.</span></span> <span data-ttu-id="cb4f5-191">Dies liegt daran, dass Sie die **allmembership Name** -Eigenschaft für die Hierarchie `All Products` in eine frühere Version der Lektion geändert haben.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-191">This is because you changed the **AllMemberName** property for the hierarchy to `All Products` earlier in the lesson.</span></span> <span data-ttu-id="cb4f5-192">Auch verfügen die Elemente der **Product Line** -Ebene jetzt über benutzerfreundliche Namen anstelle von Abkürzungen aus einem Buchstaben.</span><span class="sxs-lookup"><span data-stu-id="cb4f5-192">Also, the members of the **Product Line** level now have user-friendly names, instead of single-letter abbreviations.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="cb4f5-193">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="cb4f5-193">Next Task in Lesson</span></span>  
 [<span data-ttu-id="cb4f5-194">Ändern der Date-Dimension</span><span class="sxs-lookup"><span data-stu-id="cb4f5-194">Modifying the Date Dimension</span></span>](lesson-3-4-modifying-the-date-dimension.md)  
  
## <a name="see-also"></a><span data-ttu-id="cb4f5-195">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb4f5-195">See Also</span></span>  
 <span data-ttu-id="cb4f5-196">[Definieren Sie benannte Berechnungen in einer Datenquellen Sicht &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="cb4f5-196">[Define Named Calculations in a Data Source View &#40;Analysis Services&#41;](multidimensional-models/define-named-calculations-in-a-data-source-view-analysis-services.md) </span></span>  
 <span data-ttu-id="cb4f5-197">[Erstellen von benutzerdefinierten Hierarchien](multidimensional-models/user-defined-hierarchies-create.md) </span><span class="sxs-lookup"><span data-stu-id="cb4f5-197">[Create User-Defined Hierarchies](multidimensional-models/user-defined-hierarchies-create.md) </span></span>  
 [<span data-ttu-id="cb4f5-198">Konfigurieren der Ebene &#40;Alle&#41; für Attributhierarchien</span><span class="sxs-lookup"><span data-stu-id="cb4f5-198">Configure the &#40;All&#41; Level for Attribute Hierarchies</span></span>](multidimensional-models/database-dimensions-configure-the-all-level-for-attribute-hierarchies.md)  
  
  
