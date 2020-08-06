---
title: Definieren von benannten Mengen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 47254fd3-525f-4c35-b93d-316607652517
author: minewiskan
ms.author: owend
ms.openlocfilehash: e02f4624dc0ec25ee0c3d8950c83550ca3d9ed57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616786"
---
# <a name="defining-named-sets"></a><span data-ttu-id="2aedd-102">Definieren von benannten Mengen</span><span class="sxs-lookup"><span data-stu-id="2aedd-102">Defining Named Sets</span></span>
  <span data-ttu-id="2aedd-103">Eine benannte Menge ist ein MDX-Ausdruck (Multidimensional Expressions), der eine Menge von Dimensionselementen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2aedd-103">A named set is a Multidimensional Expressions (MDX) expression that returns a set of dimension members.</span></span> <span data-ttu-id="2aedd-104">Sie können benannte Mengen definieren und im Rahmen der Cubedefinition speichern. Sie können auch benannte Mengen in Clientanwendungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="2aedd-104">You can define named sets and save them as part of the cube definition; you can also create named sets in client applications.</span></span> <span data-ttu-id="2aedd-105">Benannte Mengen können durch Kombinieren von Cubedaten, arithmetischen Operatoren, Zahlen und Funktionen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="2aedd-105">You create named sets by combining cube data, arithmetic operators, numbers, and functions.</span></span> <span data-ttu-id="2aedd-106">Benannte Mengen können von Benutzern in MDX-Abfragen in Clientanwendungen sowie zum Definieren von Mengen in Teilcubes verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2aedd-106">Named sets can be used by users in MDX queries in client applications and can also be used to define sets in subcubes.</span></span> <span data-ttu-id="2aedd-107">Ein Teilcube bezeichnet eine Auflistung von Mengen mit Kreuzprodukten, die den Cuberaum auf den definierten Teilbereich für nachfolgende Anweisungen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="2aedd-107">A subcube is a collection of crossjoined sets that restricts the cube space to the defined subspace for subsequent statements.</span></span> <span data-ttu-id="2aedd-108">Die Definition eines eingeschränkten Cuberaums stellt ein grundlegendes Konzept der MDX-Skripterstellung dar.</span><span class="sxs-lookup"><span data-stu-id="2aedd-108">Defining a restricted cube space is a fundamental concept to MDX scripting.</span></span>

 <span data-ttu-id="2aedd-109">Benannte Mengen vereinfachen MDX-Abfragen und stellen nützliche Aliase für komplexe, häufig verwendete Mengenausdrücke bereit.</span><span class="sxs-lookup"><span data-stu-id="2aedd-109">Named sets simplify MDX queries and provide useful aliases for complex, typically used, set expressions.</span></span> <span data-ttu-id="2aedd-110">So können Sie beispielsweise eine benannte Menge namens Large Resellers definieren, die die Menge der Elemente in der Reseller-Dimension mit den meisten Mitarbeitern enthält.</span><span class="sxs-lookup"><span data-stu-id="2aedd-110">For example, you can define a named set called Large Resellers that contains the set of members in the Reseller dimension that have the most employees.</span></span> <span data-ttu-id="2aedd-111">Endbenutzer können dann die benannte Menge Large Resellers in Abfragen verwenden, oder Sie können die benannte Menge verwenden, um eine Menge in einem Teilcube zu definieren.</span><span class="sxs-lookup"><span data-stu-id="2aedd-111">End users could then use the Large Resellers named set in queries, or you could use the named set to define a set in a subcube.</span></span> <span data-ttu-id="2aedd-112">Definitionen benannter Mengen werden zwar in Cubes gespeichert, aber ihre Werte sind nur im Arbeitsspeicher vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2aedd-112">Named set definitions are stored in cubes, but their values exist only in memory.</span></span> <span data-ttu-id="2aedd-113">Mithilfe des Befehls **Neue benannte Menge** auf der Registerkarte **Berechnungen** des Cube-Designers können Sie eine benannte Menge erstellen.</span><span class="sxs-lookup"><span data-stu-id="2aedd-113">To create a named set, use the **New Named Set** command on the **Calculations** tab of Cube Designer.</span></span> <span data-ttu-id="2aedd-114">Weitere Informationen finden Sie unter [Berechnungen](multidimensional-models-olap-logical-cube-objects/calculations.md)und [Erstellen von benannten Mengen](multidimensional-models/create-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="2aedd-114">For more information, see [Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md), [Create Named Sets](multidimensional-models/create-named-sets.md).</span></span>

 <span data-ttu-id="2aedd-115">Im Rahmen der Tasks in diesem Thema definieren Sie zwei benannte Mengen: die benannte Menge Core Products und die benannte Menge Large Resellers.</span><span class="sxs-lookup"><span data-stu-id="2aedd-115">In the tasks in this topic, you will define two named sets: a Core Products named set and a Large Resellers named set.</span></span>

## <a name="defining-a-core-products-named-set"></a><span data-ttu-id="2aedd-116">Definieren der benannten Menge Core Products</span><span class="sxs-lookup"><span data-stu-id="2aedd-116">Defining a Core Products Named Set</span></span>

1.  <span data-ttu-id="2aedd-117">Wechseln Sie zur Registerkarte **Berechnungen** des Cube-Designers für den Cube des [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Tutorials, und klicken Sie auf der Symbolleiste auf **Formularansicht** .</span><span class="sxs-lookup"><span data-stu-id="2aedd-117">Switch to the **Calculations** tab of Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click **Form View** on the toolbar.</span></span>

2.  <span data-ttu-id="2aedd-118">Klicken Sie im Bereich **Skriptplaner** auf **[Total Sales Ratio to All Products]** , und klicken Sie anschließend auf der Symbolleiste der Registerkarte **Berechnungen** auf **Neue benannte Menge** .</span><span class="sxs-lookup"><span data-stu-id="2aedd-118">Click **[Total Sales Ratio to All Products]** in the **Script Organizer** pane, and then click **New Named Set** on the toolbar of the **Calculations** tab.</span></span>

     <span data-ttu-id="2aedd-119">Wenn Sie eine neue Berechnung auf der Registerkarte **Berechnungen** definieren, sollten Sie daran denken, dass Berechnungen in der Reihenfolge aufgelöst werden, in der sie im Bereich **Skriptplaner** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2aedd-119">When you define a new calculation on the **Calculations** tab, remember that calculations are resolved in the order in which they appear in the **Script Organizer** pane.</span></span> <span data-ttu-id="2aedd-120">Ihr Fokus innerhalb dieses Bereichs bestimmt beim Erstellen einer neuen Berechnung die Reihenfolge, in der die Berechnung ausgeführt wird. Eine neue Berechnung wird unmittelbar nach der Berechnung definiert, die gerade den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="2aedd-120">Your focus within that pane when you create a new calculation determines the order of the execution of the calculation; a new calculation is defined immediately after the calculation on which you are focused.</span></span>

3.  <span data-ttu-id="2aedd-121">Ändern Sie im Feld **Name** den Namen der neuen benannten Menge in `[Core Products]` .</span><span class="sxs-lookup"><span data-stu-id="2aedd-121">In the **Name** box, change the name of the new named set to `[Core Products]`.</span></span>

     <span data-ttu-id="2aedd-122">Achten Sie im Bereich **Skriptplaner** auf das spezielle Symbol, das eine benannte Menge von einem Skriptbefehl oder einem berechneten Element unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="2aedd-122">In the **Script Organizer** pane, notice the unique icon that differentiates a named set from a script command or a calculated member.</span></span>

4.  <span data-ttu-id="2aedd-123">Erweitern Sie auf der Registerkarte **Metadaten** im Bereich **Berechnungs Tools** die Option **Product**, **Kategorie**, `Members` und dann **Alle Produkte**.</span><span class="sxs-lookup"><span data-stu-id="2aedd-123">On the **Metadata** tab in the **Calculation Tools** pane, expand **Product**, expand **Category**, expand `Members`, and then expand **All Products**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="2aedd-124">Wenn Sie keine Metadaten im Bereich **Berechnungstools** anzeigen können, klicken Sie auf der Symbolleiste auf **Verbindung wiederherstellen** .</span><span class="sxs-lookup"><span data-stu-id="2aedd-124">If you cannot view any metadata in the **Calculation Tools** pane, click **Reconnect** on the toolbar.</span></span> <span data-ttu-id="2aedd-125">Funktioniert dies nicht, müssen Sie möglicherweise den Cube verarbeiten oder die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]starten.</span><span class="sxs-lookup"><span data-stu-id="2aedd-125">If this does not work, you may have to process the cube or start the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>

5.  <span data-ttu-id="2aedd-126">Ziehen Sie den Bereich **Bikes** in das Feld **Ausdruck** .</span><span class="sxs-lookup"><span data-stu-id="2aedd-126">Drag **Bikes** into the **Expression** box.</span></span>

     <span data-ttu-id="2aedd-127">Sie haben somit einen Mengenausdruck erstellt, der die Menge von Elementen zurückgibt, die sich in der Bike-Kategorie der Product-Dimension befinden.</span><span class="sxs-lookup"><span data-stu-id="2aedd-127">You now have created a set expression that will return the set of members that are in the Bike category in the Product dimension.</span></span>

## <a name="defining-a-large-resellers-named-set"></a><span data-ttu-id="2aedd-128">Definieren der benannten Menge Large Resellers</span><span class="sxs-lookup"><span data-stu-id="2aedd-128">Defining a Large Resellers Named Set</span></span>

1.  <span data-ttu-id="2aedd-129">Klicken Sie `[Core Products]` mit der rechten Maustaste in den Bereich **Skript Planer** , und klicken Sie dann auf **neue benannte Menge**.</span><span class="sxs-lookup"><span data-stu-id="2aedd-129">Right-click `[Core Products]` in the **Script Organizer** pane, and then click **New Named Set**.</span></span>

2.  <span data-ttu-id="2aedd-130">Ändern Sie im Feld **Name** den Namen dieser benannten Menge in `[Large Resellers]` .</span><span class="sxs-lookup"><span data-stu-id="2aedd-130">In the **Name** box, change the name of this named set to `[Large Resellers]`.</span></span>

3.  <span data-ttu-id="2aedd-131">Geben Sie im Feld **Ausdruck** ein `Exists()` .</span><span class="sxs-lookup"><span data-stu-id="2aedd-131">In the **Expression** box, type `Exists()`.</span></span>

     <span data-ttu-id="2aedd-132">Mithilfe der Exists-Funktion geben Sie die Menge von Elementen aus der Attributhierarchie „Name des Wiederverkäufers“ zurück, die sich mit der Menge von Elementen in der Attributhierarchie „Anzahl von Mitarbeitern“ mit den meisten Mitarbeitern überschneidet.</span><span class="sxs-lookup"><span data-stu-id="2aedd-132">You will use the Exists function to return the set of members from the Reseller Name attribute hierarchy that intersects with the set of members in the Number of Employees attribute hierarchy that has the largest number of employees.</span></span>

4.  <span data-ttu-id="2aedd-133">Erweitern Sie auf der Registerkarte **Metadaten** im Bereich **Berechnungstools** die **Reseller** -Dimension, und erweitern Sie anschließend die **Reseller Name** -Attributhierarchie.</span><span class="sxs-lookup"><span data-stu-id="2aedd-133">On the **Metadata** tab in the **Calculation Tools** pane, expand the **Reseller** dimension, and then expand the **Reseller Name** attribute hierarchy.</span></span>

5.  <span data-ttu-id="2aedd-134">Ziehen Sie die **Reseller Name** -Ebene in die Klammern für den Exists-Mengenausdruck.</span><span class="sxs-lookup"><span data-stu-id="2aedd-134">Drag the **Reseller Name** level into the parenthesis for the Exists set expression.</span></span>

     <span data-ttu-id="2aedd-135">Mithilfe der Memberfunktion können Sie alle Elemente in dieser Menge zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="2aedd-135">You will use the Members function to return all members of this set.</span></span> <span data-ttu-id="2aedd-136">Weitere Informationen finden Sie unter [Members &#40;Menge&#41; &#40;MDX&#41;](/sql/mdx/members-set-mdx).</span><span class="sxs-lookup"><span data-stu-id="2aedd-136">For more information, see [Members &#40;Set&#41; &#40;MDX&#41;](/sql/mdx/members-set-mdx).</span></span>

6.  <span data-ttu-id="2aedd-137">Geben Sie nach dem Teilmengenausdruck einen Punkt ein, und fügen Sie anschließend die Memberfunktion hinzu.</span><span class="sxs-lookup"><span data-stu-id="2aedd-137">After the partial set expression, type a period, and then add the Members function.</span></span> <span data-ttu-id="2aedd-138">Der Ausdruck sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="2aedd-138">Your expression should look like the following:</span></span>

    ```
    Exists([Reseller].[Reseller Name].[Reseller Name].Members)
    ```

     <span data-ttu-id="2aedd-139">Nachdem Sie nun die erste Menge für den vorhandenen Mengen Ausdruck definiert haben, können Sie die zweite Menge hinzufügen: die Menge der Elemente der Reseller-Dimension, die die größte Anzahl von Mitarbeitern enthält.</span><span class="sxs-lookup"><span data-stu-id="2aedd-139">Now that you have defined the first set for the Exists set expression, you are ready to add the second set-the set of members of the Reseller dimension that contains the largest number of employees.</span></span>

7.  <span data-ttu-id="2aedd-140">Erweitern Sie auf der Registerkarte **Metadaten** im Bereich **Berechnungs Tools** die Option **Number of Employees** in der Reseller-Dimension, und erweitern Sie `Members` dann **All Resellers**.</span><span class="sxs-lookup"><span data-stu-id="2aedd-140">On the **Metadata** tab in the **Calculation Tools** pane, expand **Number of Employees** in the Reseller dimension, expand `Members`, and then expand **All Resellers**.</span></span>

     <span data-ttu-id="2aedd-141">Die Elemente dieser Attributhierarchie werden nicht gruppiert.</span><span class="sxs-lookup"><span data-stu-id="2aedd-141">Notice that the members of this attribute hierarchy are not grouped.</span></span>

8.  <span data-ttu-id="2aedd-142">Öffnen Sie den Dimensions-Designer für die **Reseller** -Dimension, und klicken Sie anschließend im Bereich **Attribute** auf **Number of Employees** .</span><span class="sxs-lookup"><span data-stu-id="2aedd-142">Open Dimension Designer for the **Reseller** dimension, and then click **Number of Employees** in the **Attributes** pane.</span></span>

9. <span data-ttu-id="2aedd-143">Ändern Sie im Eigenschaftenfenster die `DiscretizationMethod` -Eigenschaft in **automatisch**, und ändern Sie dann die- `DiscretizationBucketCount` Eigenschaft in `5` .</span><span class="sxs-lookup"><span data-stu-id="2aedd-143">In the Properties window, change the `DiscretizationMethod` property to **Automatic**, and then change the `DiscretizationBucketCount` property to `5`.</span></span> <span data-ttu-id="2aedd-144">Weitere Informationen finden Sie unter [Gruppieren von Attributelementen &#40;Diskretisierung&#41;](multidimensional-models/attribute-properties-group-attribute-members.md).</span><span class="sxs-lookup"><span data-stu-id="2aedd-144">For more information, see [Group Attribute Members &#40;Discretization&#41;](multidimensional-models/attribute-properties-group-attribute-members.md).</span></span>

10. <span data-ttu-id="2aedd-145">Klicken Sie im Menü **Erstellen** von [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]auf **Analysis Services Tutorial bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="2aedd-145">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>

11. <span data-ttu-id="2aedd-146">Wechseln Sie nach der erfolgreichen Bereitstellung zum Cube-Designer für den Cube des [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Tutorials, und klicken Sie auf der Symbolleiste der Registerkarte **Berechnungen** auf **Verbindung wiederherstellen** .</span><span class="sxs-lookup"><span data-stu-id="2aedd-146">When deployment has successfully completed, switch to Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click **Reconnect** on the toolbar of the **Calculations** tab.</span></span>

12. <span data-ttu-id="2aedd-147">Erweitern Sie auf der Registerkarte **Metadaten** im Bereich **Berechnungs Tools** die Option **Number of Employees** in der **Reseller** -Dimension, und erweitern Sie `Members` dann **All Resellers**.</span><span class="sxs-lookup"><span data-stu-id="2aedd-147">On the **Metadata** tab in the **Calculation Tools** pane, expand **Number of Employees** in the **Reseller** dimension, expand `Members`, and then expand **All Resellers**.</span></span>

     <span data-ttu-id="2aedd-148">Beachten Sie, dass die Elemente dieser Attributhierarchie jetzt in fünf Gruppen enthalten sind, nummeriert von 0 bis 4.</span><span class="sxs-lookup"><span data-stu-id="2aedd-148">Notice that the members of this attribute hierarchy are now contained in five groups, numbered 0 through 4.</span></span> <span data-ttu-id="2aedd-149">Die Zahl einer Gruppe wird angezeigt, wenn Sie den Zeiger auf diese Gruppe richten, um einen InfoTip anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2aedd-149">To view the number of a group, pause the pointer over that group to view an InfoTip.</span></span> <span data-ttu-id="2aedd-150">Für den Bereich `2 -17`sollte der InfoTipp `[Reseller].[Number of Employees].&[0]`enthalten.</span><span class="sxs-lookup"><span data-stu-id="2aedd-150">For the range `2 -17`, the InfoTip should contain `[Reseller].[Number of Employees].&[0]`.</span></span>

     <span data-ttu-id="2aedd-151">Die Elemente dieser Attribut Hierarchie werden gruppiert, da die DiscretizationBucketCount-Eigenschaft auf festgelegt ist `5` und die DiscretizationMethod-Eigenschaft auf **Automatic**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2aedd-151">The members of this attribute hierarchy are grouped because the DiscretizationBucketCount property is set to `5` and the DiscretizationMethod property is set to **Automatic**.</span></span>

13. <span data-ttu-id="2aedd-152">Fügen Sie im Feld **Ausdruck** im Exists-Mengenausdruck ein Komma hinter der Memberfunktion und vor der schließenden Klammer hinzu, und ziehen Sie anschließend **83 - 100** aus dem Bereich **Metadaten** an die Position hinter dem Komma.</span><span class="sxs-lookup"><span data-stu-id="2aedd-152">In the **Expression** box, add a comma in the Exists set expression after the Members function and before the closing parenthesis, and then drag **83 - 100** from the **Metadata** pane and position it after the comma.</span></span>

     <span data-ttu-id="2aedd-153">Damit haben Sie den Exists-Mengenausdruck erstellt, der die Menge von Elementen zurückgibt, die sich mit den beiden angegebenen Mengen überschneidet (der Menge aller Wiederverkäufer und der aller Wiederverkäufer mit 83 bis 100 Mitarbeitern), wenn die benannte Menge „Large Resellers“ auf einer Achse dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2aedd-153">You have now completed the Exists set expression that will return the set of members that intersects with these two specified sets, the set of all resellers and the set of resellers who have 83 to 100 employees, when the Large Resellers named set is put on an axis.</span></span>

     <span data-ttu-id="2aedd-154">Die folgende Abbildung zeigt den Bereich **Berechnungs Ausdrücke** für die `[Large Resellers]` benannte Menge.</span><span class="sxs-lookup"><span data-stu-id="2aedd-154">The following image shows the **Calculation Expressions** pane for the `[Large Resellers]` named set.</span></span>

     <span data-ttu-id="2aedd-155">![Bereich für Berechnungsausdrücke für [Large Resellers]](../../2014/tutorials/media/l6-named-set-02.gif "Bereich für Berechnungsausdrücke für [Large Resellers]")</span><span class="sxs-lookup"><span data-stu-id="2aedd-155">![Calculation Expressions pane for [Large Resellers]](../../2014/tutorials/media/l6-named-set-02.gif "Calculation Expressions pane for [Large Resellers]")</span></span>

14. <span data-ttu-id="2aedd-156">Klicken Sie auf der Symbolleiste der Registerkarte **Berechnungen** auf **Skriptansicht**, und überprüfen Sie die beiden benannten Mengen, die gerade dem Berechnungsskript hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="2aedd-156">On the toolbar of the **Calculations** tab, click **Script View**, and then review the two named sets that you have just added to the calculation script.</span></span>

15. <span data-ttu-id="2aedd-157">Fügen Sie dem Berechnungsskript direkt vor dem ersten CREATE SET-Befehl eine neue Zeile hinzu, und geben Sie dann den folgenden Text in der gesonderten Zeile in das Skript ein:</span><span class="sxs-lookup"><span data-stu-id="2aedd-157">Add a new line in the calculation script immediately before the first CREATE SET command, and then add the following text to the script on its own line:</span></span>

    ```
    /* named sets */
    ```

     <span data-ttu-id="2aedd-158">Sie haben somit zwei benannte Mengen definiert, die im Bereich **Skriptplaner** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2aedd-158">You have now defined two named sets, which are visible in the **Script Organizer** pane.</span></span> <span data-ttu-id="2aedd-159">Sie können jetzt diese benannten Mengen bereitstellen und dann im [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Cube nach diesen Measures suchen.</span><span class="sxs-lookup"><span data-stu-id="2aedd-159">You are now ready to deploy these named sets, and then to browse these measures in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>

## <a name="browsing-the-cube-by-using-the-new-named-sets"></a><span data-ttu-id="2aedd-160">Durchsuchen des Cubes mithilfe der neuen benannten Mengen</span><span class="sxs-lookup"><span data-stu-id="2aedd-160">Browsing the Cube by Using the New Named Sets</span></span>

1.  <span data-ttu-id="2aedd-161">Klicken Sie im Menü **Erstellen** von [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf **Analysis Services Tutorial bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="2aedd-161">On the **Build** menu of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>

2.  <span data-ttu-id="2aedd-162">Klicken Sie nach erfolgreicher Bereitstellung auf die Registerkarte **Browser** , und klicken Sie anschließend auf **Verbindung wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="2aedd-162">When deployment has successfully completed, click the **Browser** tab, and then click **Reconnect**.</span></span>

3.  <span data-ttu-id="2aedd-163">Löschen Sie das Raster im Datenbereich.</span><span class="sxs-lookup"><span data-stu-id="2aedd-163">Clear the grid in the data pane.</span></span>

4.  <span data-ttu-id="2aedd-164">Fügen Sie dem Datenbereich das Measure **Reseller Sales-Sales Amount** hinzu.</span><span class="sxs-lookup"><span data-stu-id="2aedd-164">Add the **Reseller Sales-Sales Amount** measure to the data area.</span></span>

5.  <span data-ttu-id="2aedd-165">Erweitern Sie die Product-Dimension, und fügen Sie dem Zeilenbereich dann Kategorie und Unterkategorie hinzu, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2aedd-165">Expand the Product dimension, and then add Category and Subcategory to the row area, as shown in the following image.</span></span>

     <span data-ttu-id="2aedd-166">![Elemente des Subcategory-Attributs](../../2014/tutorials/media/l6-named-set-03.gif "Elemente des Subcategory-Attributs")</span><span class="sxs-lookup"><span data-stu-id="2aedd-166">![Members of the Subcategory attribute](../../2014/tutorials/media/l6-named-set-03.gif "Members of the Subcategory attribute")</span></span>

6.  <span data-ttu-id="2aedd-167">Ziehen Sie **Core Products** im Bereich **Metadaten** in der **Product** -Dimension in den Filterbereich.</span><span class="sxs-lookup"><span data-stu-id="2aedd-167">In the **Metadata** pane, in the **Product** dimension, drag **Core Products** to the filter area.</span></span>

     <span data-ttu-id="2aedd-168">Nur das **Bike** -Element des **Category** -Attributs und Elemente der **Bike** -Unterkategorien verbleiben im Cube.</span><span class="sxs-lookup"><span data-stu-id="2aedd-168">Notice that only the **Bike** member of the **Category** attribute and members of the **Bike** subcategories remain in the cube.</span></span> <span data-ttu-id="2aedd-169">Das liegt daran, dass die benannte Menge **Core Products** (Kernprodukte) zur Definition eines Teilcubes verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2aedd-169">This is because the **Core Products** named set is used to define a subcube.</span></span> <span data-ttu-id="2aedd-170">Durch diesen Teilcube werden die Elemente des **Category** -Attributs in der **Product** -Dimension innerhalb des Teilcubes auf die Elemente der benannten Menge **Core Products** beschränkt, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2aedd-170">This subcube limits the members of the **Category** attribute in the **Product** dimension within the subcube to those members of the **Core Product** named set, as shown in the following image.</span></span>

     <span data-ttu-id="2aedd-171">![Elemente der benannten Menge Core Products](../../2014/tutorials/media/l6-named-set-04.gif "Elemente der benannten Menge Core Products")</span><span class="sxs-lookup"><span data-stu-id="2aedd-171">![Members of the Core Product named set](../../2014/tutorials/media/l6-named-set-04.gif "Members of the Core Product named set")</span></span>

7.  <span data-ttu-id="2aedd-172">Erweitern Sie im Bereich **Metadaten** den Eintrag **Reseller**, und fügen Sie dem Filterbereich **Large Resellers** hinzu.</span><span class="sxs-lookup"><span data-stu-id="2aedd-172">In the **Metadata** pane, expand **Reseller**, add **Large Resellers** to the filter area.</span></span>

     <span data-ttu-id="2aedd-173">Das Reseller Sales Amount-Measure im Bereich Daten zeigt nur Verkaufssummen für große Wiederverkäufer von Fahrrädern an.</span><span class="sxs-lookup"><span data-stu-id="2aedd-173">Notice that the Reseller Sales Amount measure in the Data pane only displays sales amounts for large resellers of bikes.</span></span> <span data-ttu-id="2aedd-174">Darüber hinaus zeigt der Bereich Filter jetzt die beiden benannten Mengen an, die für die Definition dieses bestimmten Teilcubes verwendet werden, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2aedd-174">Notice also that the Filter pane now displays the two named sets that are used to define this particular subcube, as shown in the following image.</span></span>

     <span data-ttu-id="2aedd-175">![Filterbereich mit zwei benannten Mengen](../../2014/tutorials/media/l6-named-set-05.gif "Filterbereich mit zwei benannten Mengen")</span><span class="sxs-lookup"><span data-stu-id="2aedd-175">![Filter pane containing two named sets](../../2014/tutorials/media/l6-named-set-05.gif "Filter pane containing two named sets")</span></span>

## <a name="next-task-in-lesson"></a><span data-ttu-id="2aedd-176">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="2aedd-176">Next Task in Lesson</span></span>
 [<span data-ttu-id="2aedd-177">Lektion 7: Definieren von KPIs &#40;Key Performance Indicator&#41;</span><span class="sxs-lookup"><span data-stu-id="2aedd-177">Lesson 7: Defining Key Performance Indicators &#40;KPIs&#41;</span></span>](lesson-7-defining-key-performance-indicators-kpis.md)

## <a name="see-also"></a><span data-ttu-id="2aedd-178">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2aedd-178">See Also</span></span>
 <span data-ttu-id="2aedd-179">[Berechnungen](multidimensional-models-olap-logical-cube-objects/calculations.md) [Erstellen benannter Mengen](multidimensional-models/create-named-sets.md)</span><span class="sxs-lookup"><span data-stu-id="2aedd-179">[Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md) [Create Named Sets](multidimensional-models/create-named-sets.md)</span></span>

