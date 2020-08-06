---
title: Definieren von Eigenschaften des übergeordneten Attributs in einer Hierarchie mit über-und Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2d78fa73-a13b-4e12-bbd0-43e5307f760c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1dfa4340bdc161809cf3821e5cb1f0609399e1d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619421"
---
# <a name="defining-parent-attribute-properties-in-a-parent-child-hierarchy"></a><span data-ttu-id="03d17-102">Definieren der Eigenschaften des übergeordneten Attributs in einer Über-/Unterordnungshierarchie</span><span class="sxs-lookup"><span data-stu-id="03d17-102">Defining Parent Attribute Properties in a Parent-Child Hierarchy</span></span>
  <span data-ttu-id="03d17-103">Eine Hierarchie mit über- und untergeordneten Elementen ist eine Hierarchie in einer Dimension, die auf zwei Tabellenspalten basiert.</span><span class="sxs-lookup"><span data-stu-id="03d17-103">A parent-child hierarchy is a hierarchy in a dimension that is based on two table columns.</span></span> <span data-ttu-id="03d17-104">Zusammen definieren diese Spalten die hierarchischen Beziehungen zwischen den Elementen der Dimension.</span><span class="sxs-lookup"><span data-stu-id="03d17-104">Together, these columns define the hierarchical relationships among the members of the dimension.</span></span> <span data-ttu-id="03d17-105">Die erste Spalte, die so genannte *Elementschlüsselspalte*, identifiziert jedes Dimensionselement.</span><span class="sxs-lookup"><span data-stu-id="03d17-105">The first column, called the *member key column*, identifies each dimension member.</span></span> <span data-ttu-id="03d17-106">Die zweite Spalte, die so genannte *übergeordnete Spalte*, identifiziert das übergeordnete Element der einzelnen Dimensionselemente.</span><span class="sxs-lookup"><span data-stu-id="03d17-106">The other column, called the *parent column*, identifies the parent of each dimension member.</span></span> <span data-ttu-id="03d17-107">Die **NamingTemplate** -Eigenschaft eines übergeordneten Attributs bestimmt den Namen jeder Ebene in der Über-/Unterordnungshierarchie, und die **MembersWithData** -Eigenschaft bestimmt, ob Daten für übergeordnete Elemente angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="03d17-107">The **NamingTemplate** property of a parent attribute determines the name of each level in the parent-child hierarchy, and the **MembersWithData** property determines whether data for parent members should be displayed.</span></span>

 <span data-ttu-id="03d17-108">Weitere Informationen finden Sie unter über [-](multidimensional-models/parent-child-dimension.md)/unterordnungshierarchie, [Attribute in über-und untergeordneten Hierarchien](multidimensional-models/parent-child-dimension-attributes.md) .</span><span class="sxs-lookup"><span data-stu-id="03d17-108">For more information, see [Parent-Child Hierarchy](multidimensional-models/parent-child-dimension.md), [Attributes in Parent-Child Hierarchies](multidimensional-models/parent-child-dimension-attributes.md)</span></span>

> [!NOTE]
>  <span data-ttu-id="03d17-109">Wenn Sie zum Erstellen einer Dimension den Dimensions-Assistenten verwenden, werden vom Assistenten Tabellen erkannt, die Über-/Unterordnungsbeziehungen enthalten, und die Über-/Unterordnungshierarchie wird automatisch definiert.</span><span class="sxs-lookup"><span data-stu-id="03d17-109">When you use the Dimension Wizard to create a dimension, the wizard recognizes the tables that have parent-child relationships and automatically defines the parent-child hierarchy for you.</span></span>

 <span data-ttu-id="03d17-110">In den Aufgaben dieses Themas erstellen Sie eine Benennungsvorlage, durch die der Name für jede Ebene in der Über-/Unterordnungshierarchie in der **Employee** -Dimension definiert wird.</span><span class="sxs-lookup"><span data-stu-id="03d17-110">In the tasks in this topic, you will create a naming template that defines the name for each level in the parent-child hierarchy in the **Employee** dimension.</span></span> <span data-ttu-id="03d17-111">Anschließend konfigurieren Sie das übergeordnete Attribut zum Ausblenden aller übergeordneten Daten, sodass nur die Verkäufe für Blattebenenelemente angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="03d17-111">You will then configure the parent attribute to hide all parent data, so that only the sales for leaf-level members are displayed.</span></span>

## <a name="browsing-the-employee-dimension"></a><span data-ttu-id="03d17-112">Durchsuchen der Employee-Dimension</span><span class="sxs-lookup"><span data-stu-id="03d17-112">Browsing the Employee Dimension</span></span>

1.  <span data-ttu-id="03d17-113">Doppelklicken Sie im Projektmappen-Explorer im Ordner **Dimensionen** auf **Employee.dim** , um den Dimensions-Designer für die Employee-Dimension zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="03d17-113">In Solution Explorer, double-click **Employee.dim** in the **Dimensions** folder to open Dimension Designer for the Employee dimension.</span></span>

2.  <span data-ttu-id="03d17-114">Klicken Sie auf die Registerkarte **Browser** , überprüfen Sie, ob in der Liste **Hierarchie** der Eintrag **Employees** ausgewählt ist, und erweitern Sie anschließend das **All Employees** -Element.</span><span class="sxs-lookup"><span data-stu-id="03d17-114">Click the **Browser** tab, verify that **Employees** is selected in the **Hierarchy** list, and then expand the **All Employees** member.</span></span>

     <span data-ttu-id="03d17-115">Beachten Sie, dass **Ken J. Sánchez** der Manager der obersten Ebene in dieser Über-/Unterordnungshierarchie ist.</span><span class="sxs-lookup"><span data-stu-id="03d17-115">Notice that **Ken J. Sánchez** is the top-level manager in this parent-child hierarchy.</span></span>

3.  <span data-ttu-id="03d17-116">Wählen Sie das Element **Ken J. Sánchez** aus.</span><span class="sxs-lookup"><span data-stu-id="03d17-116">Select the **Ken J. Sánchez** member.</span></span>

     <span data-ttu-id="03d17-117">Beachten Sie, dass der Ebenenname für dieses Element **Level 02**ist.</span><span class="sxs-lookup"><span data-stu-id="03d17-117">Notice that the level name for this member is **Level 02**.</span></span> <span data-ttu-id="03d17-118">(Der Ebenenname wird nach **Aktuelle Ebene** direkt über dem **All Employees** -Element angezeigt.) In der nächsten Aufgabe definieren Sie mehr beschreibende Namen für jede Ebene.</span><span class="sxs-lookup"><span data-stu-id="03d17-118">(The level name appears after **Current level:** immediately above the **All Employees** member.) In the next task, you will define more descriptive names for each level.</span></span>

4.  <span data-ttu-id="03d17-119">Erweitern Sie **Ken J. Sánchez** , um die Namen der Angestellten anzuzeigen, die Berichte für diesen Manager verfassen, und wählen Sie anschließend **Brian S. Welcker** aus, um den Namen dieser Ebene anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="03d17-119">Expand **Ken J. Sánchez** to view the names of the employees who report to this manager, and then select **Brian S. Welcker** to view the name of this level.</span></span>

     <span data-ttu-id="03d17-120">Beachten Sie, dass der Ebenenname für dieses Element **Level 03**ist.</span><span class="sxs-lookup"><span data-stu-id="03d17-120">Notice that the level name for this member is **Level 03**.</span></span>

5.  <span data-ttu-id="03d17-121">Doppelklicken Sie im Projektmappen-Explorer im Ordner **Cubes** auf **Analysis Services Tutorial.cube** , um den Cube-Designer für den [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Cube zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="03d17-121">In Solution Explorer, double-click **Analysis Services Tutorial.cube** in the **Cubes** folder to open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube.</span></span>

6.  <span data-ttu-id="03d17-122">Klicken Sie auf die Registerkarte **Browser** .</span><span class="sxs-lookup"><span data-stu-id="03d17-122">Click the **Browser** tab.</span></span>

7.  <span data-ttu-id="03d17-123">Klicken Sie auf das Excel-Symbol und anschließend auf **Aktivieren** , sobald Sie zum Aktivieren von Verbindungen aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="03d17-123">Click the Excel icon, and then click **Enable** when prompted to enable connections.</span></span>

8.  <span data-ttu-id="03d17-124">Erweitern Sie in der PivotTable-Feldliste **Reseller Sales**.</span><span class="sxs-lookup"><span data-stu-id="03d17-124">In the PivotTable Field List, expand **Reseller Sales**.</span></span> <span data-ttu-id="03d17-125">Ziehen Sie **Reseller Sales-Sales Amount** in den Bereich Werte.</span><span class="sxs-lookup"><span data-stu-id="03d17-125">Drag **Reseller Sales-Sales Amount** to the Values area.</span></span>

9. <span data-ttu-id="03d17-126">Erweitern Sie in der PivotTable-Feldliste **Employee**, und ziehen Sie anschließend die **Employees** -Hierarchie in den Bereich **Zeilen** .</span><span class="sxs-lookup"><span data-stu-id="03d17-126">In the PivotTable Field List, expand **Employee**, and then drag the **Employees** hierarchy to the **Rows** area.</span></span>

     <span data-ttu-id="03d17-127">Alle Elemente der Employees-Hierarchie werden der Spalte A des PivotTable-Berichts hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="03d17-127">All the members of the Employees hierarchy are added to column A of the PivotTable report.</span></span>

     <span data-ttu-id="03d17-128">In der folgenden Abbildung wird die erweiterte Employees-Hierarchie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="03d17-128">The following image shows the Employees hierarchy expanded.</span></span>

10. <span data-ttu-id="03d17-129">![PivotTable mit der Employees-Hierarchie](../../2014/tutorials/media/l4-employee-1.gif "PivotTable mit der Employees-Hierarchie")</span><span class="sxs-lookup"><span data-stu-id="03d17-129">![PivotTable showing Employees hierarchy](../../2014/tutorials/media/l4-employee-1.gif "PivotTable showing Employees hierarchy")</span></span>

     <span data-ttu-id="03d17-130">Beachten Sie, dass die von jedem Manager in Ebene 03 gemachten Verkäufe auch in Ebene 04 angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="03d17-130">Notice that the sales made by each manager in Level 03 are also displayed in Level 04.</span></span> <span data-ttu-id="03d17-131">Das liegt daran, dass jeder Manager auch ein Mitarbeiter eines anderen Managers ist.</span><span class="sxs-lookup"><span data-stu-id="03d17-131">This is because each manager is also an employee of another manager.</span></span> <span data-ttu-id="03d17-132">In der nächsten Aufgabe blenden Sie diese Verkaufszahlen aus.</span><span class="sxs-lookup"><span data-stu-id="03d17-132">In the next task, you will hide these sale amounts.</span></span>

## <a name="modifying-parent-attribute-properties-in-the-employee-dimension"></a><span data-ttu-id="03d17-133">Ändern von Eigenschaften des übergeordneten Attributs in der Employee-Dimension.</span><span class="sxs-lookup"><span data-stu-id="03d17-133">Modifying Parent Attribute Properties in the Employee Dimension</span></span>

1.  <span data-ttu-id="03d17-134">Wechseln Sie zum Dimensions-Designer für die **Employee** -Dimension.</span><span class="sxs-lookup"><span data-stu-id="03d17-134">Switch to Dimension Designer for the **Employee** dimension.</span></span>

2.  <span data-ttu-id="03d17-135">Klicken Sie auf die Registerkarte **Dimensionsstruktur** , und wählen Sie anschließend die **Employees** -Attributhierarchie im Bereich **Attribute** aus.</span><span class="sxs-lookup"><span data-stu-id="03d17-135">Click the **Dimension Structure** tab, and then select the **Employees** attribute hierarchy in the **Attributes** pane.</span></span>

     <span data-ttu-id="03d17-136">Beachten Sie das eindeutige Symbol für dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="03d17-136">Notice the unique icon for this attribute.</span></span> <span data-ttu-id="03d17-137">Dieses Symbol gibt an, dass das Attribut der übergeordnete Schlüssel in einer Über-/Unterordnungshierarchie ist.</span><span class="sxs-lookup"><span data-stu-id="03d17-137">This icon signifies that the attribute is the parent key in a parent-child hierarchy.</span></span> <span data-ttu-id="03d17-138">Beachten Sie ebenso, dass im Eigenschaftenfenster die **Verwendung** -Eigenschaft für das Attribut als **Übergeordnet**definiert ist.</span><span class="sxs-lookup"><span data-stu-id="03d17-138">Notice also, in the Properties window, that the **Usage** property for the attribute is defined as **Parent**.</span></span> <span data-ttu-id="03d17-139">Diese Eigenschaft wurde vom Dimensions-Assistenten festgelegt, als die Dimension entworfen wurde.</span><span class="sxs-lookup"><span data-stu-id="03d17-139">This property was set by the Dimension Wizard when the dimension was designed.</span></span> <span data-ttu-id="03d17-140">Der Assistent hat die Über-/Unterordnungsbeziehung automatisch erkannt.</span><span class="sxs-lookup"><span data-stu-id="03d17-140">The wizard automatically detected the parent-child relationship.</span></span>

3.  <span data-ttu-id="03d17-141">Klicken Sie im Eigenschaftenfenster auf die Schaltfläche mit den drei Punkten (**...**) in der **NamingTemplate** -Eigenschaftenzelle.</span><span class="sxs-lookup"><span data-stu-id="03d17-141">In the Properties window, click the ellipsis button (**...**) in the **NamingTemplate** property cell.</span></span>

     <span data-ttu-id="03d17-142">Im Dialogfeld **Vorlage zur Ebenenbenennung** definieren Sie die Vorlage zur Ebenenbenennung, durch die die Ebenennamen in der Über-/Unterordnungshierarchie bestimmt werden, die Benutzern beim Durchsuchen von Cubes angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="03d17-142">In the **Level Naming Template** dialog box, you define the level naming template that determines the level names in the parent-child hierarchy that are displayed to users as they browse cubes.</span></span>

4.  <span data-ttu-id="03d17-143">Geben Sie in der zweiten Zeile in der **\*** Spalte Name den **Wert Employee \* Level** in die Spalte **Name** ein, und klicken Sie dann auf die dritte Zeile.</span><span class="sxs-lookup"><span data-stu-id="03d17-143">In the second row, the **\*** row, type **Employee Level \*** in the **Name** column, and then click the third row.</span></span>

     <span data-ttu-id="03d17-144">Beachten Sie unter **Ergebnis** , dass jede Ebene jetzt „Employee Level“ gefolgt von einer zunehmenden Nummer benannt wird.</span><span class="sxs-lookup"><span data-stu-id="03d17-144">Notice under **Result** that each level will now be named "Employee Level" followed by a sequentially increasing number.</span></span>

     <span data-ttu-id="03d17-145">Die folgende Abbildung zeigt die Änderungen im Dialogfeld **Vorlage zur Ebenenbenennung** .</span><span class="sxs-lookup"><span data-stu-id="03d17-145">The following image shows the changes in the **Level Naming Template** dialog box.</span></span>

     <span data-ttu-id="03d17-146">![Vorlage für ebenenbenennungs Vorlage](../../2014/tutorials/media/l4-namingtemplate.gif "Vorlage zur Ebenenbenennung (Dialogfeld)")</span><span class="sxs-lookup"><span data-stu-id="03d17-146">![Level Naming Template dialog box](../../2014/tutorials/media/l4-namingtemplate.gif "Level Naming Template dialog box")</span></span>

5.  <span data-ttu-id="03d17-147">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="03d17-147">Click **OK**.</span></span>

6.  <span data-ttu-id="03d17-148">Wählen Sie im Eigenschaftenfenster für das **Employees** -Attribut in der **MembersWithData** -Eigenschaftenzelle **NonLeafDataHidden** aus, um diesen Wert für das **Employees** -Attribut zu ändern.</span><span class="sxs-lookup"><span data-stu-id="03d17-148">In the Properties window for the **Employees** attribute, in the **MembersWithData** property cell, select **NonLeafDataHidden** to change this value for the **Employees** attribute.</span></span>

     <span data-ttu-id="03d17-149">Dadurch werden Daten ausgeblendet, die mit Mitgliedern auf einer Nichtblattebene in der Über-/Unterordnungshierarchie verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="03d17-149">This will cause data that is related to non-leaf level members in the parent-child hierarchy to be hidden.</span></span>

## <a name="browsing-the-employee-dimension-with-the-modified-attributes"></a><span data-ttu-id="03d17-150">Durchsuchen der Employee-Dimension mit den geänderten Attributen</span><span class="sxs-lookup"><span data-stu-id="03d17-150">Browsing the Employee Dimension with the Modified Attributes</span></span>

1.  <span data-ttu-id="03d17-151">Klicken Sie im Menü **Erstellen** von [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]auf **Analysis Services Tutorial bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="03d17-151">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>

2.  <span data-ttu-id="03d17-152">Wechseln Sie nach erfolgreichem Abschluss der Bereitstellung zum Cube-Designer für den [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Cube, und klicken Sie auf der Symbolleiste der Registerkarte **Browser** auf **Verbindung wiederherstellen** .</span><span class="sxs-lookup"><span data-stu-id="03d17-152">When deployment has successfully completed, switch to Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click **Reconnect** on the toolbar of the **Browser** tab.</span></span>

3.  <span data-ttu-id="03d17-153">Klicken Sie auf das Excel-Symbol und anschließend auf **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="03d17-153">Click the Excel icon, and then click **Enable**.</span></span>

4.  <span data-ttu-id="03d17-154">Ziehen Sie **Reseller Sales-Sales Amount** in den Bereich Werte.</span><span class="sxs-lookup"><span data-stu-id="03d17-154">Drag **Reseller Sales-Sales Amount** to the Values area.</span></span>

5.  <span data-ttu-id="03d17-155">Ziehen Sie die **Employees** -Hierarchie in den Bereich Zeilenbezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="03d17-155">Drag the **Employees** hierarchy to the Row Labels area.</span></span>

     <span data-ttu-id="03d17-156">Die folgende Abbildung zeigt die Änderungen, die Sie an der Employees-Hierarchie vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="03d17-156">The following image shows the changes that you made to the Employees hierarchy.</span></span> <span data-ttu-id="03d17-157">Beachten Sie, dass Stephen Y. Jiang nicht mehr als sein eigener Mitarbeiter angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="03d17-157">Notice that Stephen Y. Jiang no longer appears as an employee of himself.</span></span>

     <span data-ttu-id="03d17-158">![Geänderte Employees-Hierarchie](../../2014/tutorials/media/l4-employee-2.png "Geänderte Employees-Hierarchie")</span><span class="sxs-lookup"><span data-stu-id="03d17-158">![Modified Employees hierarchy](../../2014/tutorials/media/l4-employee-2.png "Modified Employees hierarchy")</span></span>

## <a name="next-task-in-lesson"></a><span data-ttu-id="03d17-159">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="03d17-159">Next Task in Lesson</span></span>
 [<span data-ttu-id="03d17-160">Automatisches Gruppieren von Attributelementen</span><span class="sxs-lookup"><span data-stu-id="03d17-160">Automatically Grouping Attribute Members</span></span>](lesson-4-3-automatically-grouping-attribute-members.md)

## <a name="see-also"></a><span data-ttu-id="03d17-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="03d17-161">See Also</span></span>
 <span data-ttu-id="03d17-162">[Attribute der](multidimensional-models/parent-child-dimension-attributes.md) über [-und untergeordneten Hierarchie](multidimensional-models/parent-child-dimension.md) in über-/Unterordnung</span><span class="sxs-lookup"><span data-stu-id="03d17-162">[Parent-Child Hierarchy](multidimensional-models/parent-child-dimension.md) [Attributes in Parent-Child Hierarchies](multidimensional-models/parent-child-dimension-attributes.md)</span></span>


