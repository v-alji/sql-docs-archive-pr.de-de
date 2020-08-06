---
title: Definieren berechneter Elemente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 07f13e1c-0b20-4f9e-ad62-c438983f2785
author: minewiskan
ms.author: owend
ms.openlocfilehash: f2a054356613ebf3d4cf825c1fa4c238a5362ec3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616785"
---
# <a name="defining-calculated-members"></a><span data-ttu-id="e3ad7-102">Definieren berechneter Elemente</span><span class="sxs-lookup"><span data-stu-id="e3ad7-102">Defining Calculated Members</span></span>
  <span data-ttu-id="e3ad7-103">Berechnete Elemente sind Elemente einer Dimension oder Measuregruppe, die auf Basis einer Kombination aus Cubedaten, arithmetischen Operatoren, Zahlen und Funktionen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-103">Calculated members are members of a dimension or a measure group that are defined based on a combination of cube data, arithmetic operators, numbers, and functions.</span></span> <span data-ttu-id="e3ad7-104">Sie können beispielsweise ein berechnetes Element erstellen, das die Summe zweier physischer Measures im Cube berechnet.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-104">For example, you can create a calculated member that calculates the sum of two physical measures in the cube.</span></span> <span data-ttu-id="e3ad7-105">Die Definitionen berechneter Elemente werden in Cubes gespeichert, ihre Werte werden jedoch erst zum Zeitpunkt der Abfrage berechnet.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-105">Calculated member definitions are stored in cubes, but their values are calculated at query time.</span></span>  
  
 <span data-ttu-id="e3ad7-106">Mithilfe des Befehls **Neues berechnetes Element** auf der Registerkarte **Berechnungen** des Cube-Designers können Sie ein berechnetes Element erstellen.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-106">To create a calculated member, use the **New Calculated Member** command on the **Calculations** tab of Cube Designer.</span></span> <span data-ttu-id="e3ad7-107">Sie können ein berechnetes Element in jeder beliebigen Dimension erstellen, einschließlich der Measuredimension.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-107">You can create a calculated member within any dimension, including the measures dimension.</span></span> <span data-ttu-id="e3ad7-108">Sie können ein berechnetes Element auch innerhalb eines Anzeigeordners im Dialogfeld **Berechnungseigenschaften** platzieren.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-108">You can also place a calculated member within a display folder in the **Calculation Properties** dialog box.</span></span> <span data-ttu-id="e3ad7-109">Weitere Informationen finden Sie unter [Berechnungen](multidimensional-models-olap-logical-cube-objects/calculations.md), [Berechnungen in mehrdimensionalen Modellen](multidimensional-models/calculations-in-multidimensional-models.md)und [Erstellen von berechneten Elementen](multidimensional-models/create-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="e3ad7-109">For more information, see [Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md), [Calculations in Multidimensional Models](multidimensional-models/calculations-in-multidimensional-models.md), and [Create Calculated Members](multidimensional-models/create-calculated-members.md).</span></span>  
  
 <span data-ttu-id="e3ad7-110">Im Rahmen der Tasks in diesem Thema definieren Sie berechnete Measures, damit Benutzer den Prozentsatz der Bruttorendite und die Verkaufsverhältnisse für Internetverkäufe, Verkäufe des Wiederverkäufers und alle Verkäufe anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-110">In the tasks in this topic, you define calculated measures to let users view the gross profit margin percentage and sales ratios for Internet sales, reseller sales, and for all sales.</span></span>  
  
## <a name="defining-calculations-to-aggregate-physical-measures"></a><span data-ttu-id="e3ad7-111">Definieren von Berechnungen zum Aggregieren physischer Measures</span><span class="sxs-lookup"><span data-stu-id="e3ad7-111">Defining Calculations to Aggregate Physical Measures</span></span>  
  
1.  <span data-ttu-id="e3ad7-112">Wechseln Sie zum Cube-Designer für den [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial-Cube, und klicken Sie anschließend auf die Registerkarte **Berechnungen** .</span><span class="sxs-lookup"><span data-stu-id="e3ad7-112">Open Cube Designer for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial cube, and then click the **Calculations** tab.</span></span>  
  
     <span data-ttu-id="e3ad7-113">In den Bereichen **Berechnungsausdrücke** und **Skriptplaner** wird standardmäßig der CALCULATE-Befehl angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-113">Notice the default CALCULATE command in the **Calculation Expressions** pane and in the **Script Organizer** pane.</span></span> <span data-ttu-id="e3ad7-114">Dieser Befehl gibt an, dass die Measures im Cube gemäß dem durch die AggregateFunction-Eigenschaften angegebenen Wert aggregiert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-114">This command specifies that the measures in the cube should be aggregated according to the value that is specified by their AggregateFunction properties.</span></span> <span data-ttu-id="e3ad7-115">Measurewerte werden im Allgemeinen summiert, können jedoch auch auf andere Weise gezählt oder aggregiert werden.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-115">Measure values are generally summed, but may also be counted or aggregated in some other manner.</span></span>  
  
     <span data-ttu-id="e3ad7-116">In der folgenden Abbildung ist die Registerkarte **Berechnungen** des Cube-Designers dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-116">The following image shows the **Calculations** tab of Cube Designer.</span></span>  
  
     <span data-ttu-id="e3ad7-117">![Berechnungen (Registerkarte) des Cube-Designers](../../2014/tutorials/media/l6-calculatedmembers-1.gif "Berechnungen (Registerkarte) des Cube-Designers")</span><span class="sxs-lookup"><span data-stu-id="e3ad7-117">![Calculations tab of Cube Designer](../../2014/tutorials/media/l6-calculatedmembers-1.gif "Calculations tab of Cube Designer")</span></span>  
  
2.  <span data-ttu-id="e3ad7-118">Klicken Sie auf der Symbolleiste der Registerkarte **Berechnungen** auf **Neues berechnetes Element**.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-118">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
     <span data-ttu-id="e3ad7-119">Im Bereich **Berechnungsausdrücke** wird ein neues Formular angezeigt, in dem Sie die Eigenschaften des neuen berechneten Elements definieren können.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-119">A new form appears in the **Calculation Expressions** pane within which you define the properties of this new calculated member.</span></span> <span data-ttu-id="e3ad7-120">Das neue Element wird auch im Bereich **Skriptplaner** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-120">The new member also appears in the **Script Organizer** pane.</span></span>  
  
     <span data-ttu-id="e3ad7-121">In der folgenden Abbildung ist das Formular dargestellt, das im Bereich **Berechnungsausdrücke** angezeigt wird, wenn Sie auf **Neues berechnetes Element**klicken.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-121">The following image shows the form that appears in the **Calculation Expressions** pane when you click **New Calculated Member**.</span></span>  
  
     <span data-ttu-id="e3ad7-122">![Bereichsformular für Berechnungsausdrücke](../../2014/tutorials/media/l6-calculatedmembers-02.gif "Bereichsformular für Berechnungsausdrücke")</span><span class="sxs-lookup"><span data-stu-id="e3ad7-122">![Calculation Expressions pane form](../../2014/tutorials/media/l6-calculatedmembers-02.gif "Calculation Expressions pane form")</span></span>  
  
3.  <span data-ttu-id="e3ad7-123">Ändern Sie im Feld **Name** den Namen des berechneten Measures in `[Total Sales Amount]` .</span><span class="sxs-lookup"><span data-stu-id="e3ad7-123">In the **Name** box, change the name of the calculated measure to `[Total Sales Amount]`.</span></span>  
  
     <span data-ttu-id="e3ad7-124">Enthält der Name eines berechneten Elements ein Leerzeichen, muss er in eckige Klammern eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-124">If the name of a calculated member contains a space, the calculated member name must be enclosed in square brackets.</span></span>  
  
     <span data-ttu-id="e3ad7-125">In der Liste **Übergeordnete Hierarchie** wird standardmäßig ein neues berechnetes Element in der **Measures** -Dimension erstellt.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-125">Notice in the **Parent hierarchy** list that, by default, a new calculated member is created in the **Measures** dimension.</span></span> <span data-ttu-id="e3ad7-126">Ein berechnetes Element in der Measures-Dimension wird auch häufig als berechnetes Measure bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-126">A calculated member in the Measures dimension is also frequently called a calculated measure.</span></span>  
  
4.  <span data-ttu-id="e3ad7-127">Erweitern Sie auf der Registerkarte **Metadaten** im Bereich **Berechnungstools** der Registerkarte **Berechnungen** zuerst die Option **Measures** und anschließend **Internet Sales** , um die Metadaten für die **Internet Sales** -Measuregruppe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-127">On the **Metadata** tab in the **Calculation Tools** pane of the **Calculations** tab, expand **Measures** and then expand **Internet Sales** to view the metadata for the **Internet Sales** measure group.</span></span>  
  
     <span data-ttu-id="e3ad7-128">Metadatenelemente können aus dem Bereich **Berechnungstools** in das Feld **Ausdruck** gezogen und anschließend können ihnen Operatoren sowie andere Elemente hinzugefügt werden, um MDX-Ausdrücke (Multidimensional Expressions) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-128">You can drag metadata elements from the **Calculation Tools** pane into the **Expression** box and then add operators and other elements to create Multidimensional Expressions (MDX) expressions.</span></span> <span data-ttu-id="e3ad7-129">Alternativ können Sie den MDX-Ausdruck direkt in das Feld **Ausdruck** eingeben.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-129">Alternatively, you can type the MDX expression directly into the **Expression** box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e3ad7-130">Wenn Sie keine Metadaten im Bereich **Berechnungstools** anzeigen können, klicken Sie auf der Symbolleiste auf **Verbindung wiederherstellen** .</span><span class="sxs-lookup"><span data-stu-id="e3ad7-130">If you cannot view any metadata in the **Calculation Tools** pane, click **Reconnect** on the toolbar.</span></span> <span data-ttu-id="e3ad7-131">Funktioniert dies nicht, müssen Sie möglicherweise den Cube verarbeiten oder die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]starten.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-131">If this does not work, you may have to process the cube or start the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
5.  <span data-ttu-id="e3ad7-132">Ziehen Sie **Internet Sales-Sales Amount** von der Registerkarte **Metadaten** im Bereich **Berechnungstools** in das Feld **Ausdruck** im Bereich **Berechnungsausdrücke** .</span><span class="sxs-lookup"><span data-stu-id="e3ad7-132">Drag **Internet Sales-Sales Amount** from the **Metadata** tab in the **Calculation Tools** pane into the **Expression** box in the **Calculation Expressions** pane.</span></span>  
  
6.  <span data-ttu-id="e3ad7-133">Geben Sie im Feld **Ausdruck** ein Pluszeichen (`+`) nach **[Measures].[Internet Sales-Sales Amount]** ein.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-133">In the **Expression** box, type a plus sign (`+`) after **[Measures].[Internet Sales-Sales Amount]**.</span></span>  
  
7.  <span data-ttu-id="e3ad7-134">Erweitern Sie auf der Registerkarte **Metadaten** im Bereich **Berechnungstools** die Option **Reseller Sales**, und ziehen Sie anschließend **Reseller Sales-Sales Amount** in das Feld **Ausdruck** im Bereich **Berechnungsausdrücke** hinter das Pluszeichen (+).</span><span class="sxs-lookup"><span data-stu-id="e3ad7-134">On the **Metadata** tab in the **Calculation Tools** pane, expand **Reseller Sales**, and then drag **Reseller Sales-Sales Amount** into the **Expression** box in the **Calculation Expressions** pane after the plus sign (+).</span></span>  
  
8.  <span data-ttu-id="e3ad7-135">Wählen Sie in der Liste **Format Zeichenfolge** die Option **"Currency" aus.**</span><span class="sxs-lookup"><span data-stu-id="e3ad7-135">In the **Format string** list, select **"Currency".**</span></span>  
  
9. <span data-ttu-id="e3ad7-136">Aktivieren Sie in der Liste **Verhalten für nicht leere Elemente** die Kontrollkästchen für **Internet Sales-Sales Amount** und **Reseller Sales-Sales Amount**, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-136">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e3ad7-137">Die in der Liste **Verhalten für nicht leere Elemente** angegebenen Measures werden zum Auflösen von NON EMPTY-Abfragen in MDX verwendet.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-137">The measures you specify in the **Non-empty behavior** list are used to resolve NON EMPTY queries in MDX.</span></span> <span data-ttu-id="e3ad7-138">Wenn Sie ein oder mehrere Measures in der Liste **Verhalten für nicht leere Elemente** angeben, behandelt [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] das berechnete Element als leer, wenn alle angegebenen Measures leer sind.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-138">When you specify one or more measures in the **Non-empty behavior** list, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] treats the calculated member as empty if all the specified measures are empty.</span></span> <span data-ttu-id="e3ad7-139">Wenn die **Non-empty behavior** -Eigenschaft leer ist, muss [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] das berechnete Element selbst auswerten, um zu ermitteln, ob das Element leer ist.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-139">If the **Non-empty behavior** property is blank, [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] must evaluate the calculated member itself to determine whether the member is empty.</span></span>  
  
     <span data-ttu-id="e3ad7-140">Die folgende Abbildung stellt den Bereich **Berechnungsausdrücke** dar, der mit den in den vorhergehenden Schritten angegebenen Einstellungen aufgefüllt wurde.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-140">The following image shows the **Calculation Expressions** pane populated with the settings that you specified in the previous steps.</span></span>  
  
     <span data-ttu-id="e3ad7-141">![Aufgefüllter Bereich für Berechnungsausdrücke](../../2014/tutorials/media/l6-calculatedmembers-03.gif "Aufgefüllter Bereich für Berechnungsausdrücke")</span><span class="sxs-lookup"><span data-stu-id="e3ad7-141">![Populated Calculation Expressions pane](../../2014/tutorials/media/l6-calculatedmembers-03.gif "Populated Calculation Expressions pane")</span></span>  
  
10. <span data-ttu-id="e3ad7-142">Klicken Sie auf der Symbolleiste der Registerkarte **Berechnungen** auf **Skriptansicht**, und überprüfen Sie anschließend das Berechnungsskript im Bereich **Berechnungsausdrücke** .</span><span class="sxs-lookup"><span data-stu-id="e3ad7-142">On the toolbar of the **Calculations** tab, click **Script View**, and then review the calculation script in the **Calculation Expressions** pane.</span></span>  
  
     <span data-ttu-id="e3ad7-143">Die neue Berechnung wird dem CALCULATE-Ausgangsausdruck hinzugefügt; die einzelnen Berechnungen werden durch ein Semikolon voneinander getrennt.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-143">Notice that the new calculation is added to the initial CALCULATE expression; each individual calculation is separated by a semicolon.</span></span> <span data-ttu-id="e3ad7-144">Am Anfang des Berechnungsskripts wird ein Kommentar angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-144">Notice also that a comment appears at the beginning of the calculation script.</span></span> <span data-ttu-id="e3ad7-145">Das Berechnungsskript durch Kommentare für Berechnungsgruppen zu ergänzen, ist sinnvoll, um Ihnen und anderen Entwicklern das Verständnis komplexer Berechnungsskripts zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-145">Adding comments within the calculation script for groups of calculations is a good practice, to help you and other developers understand complex calculation scripts.</span></span>  
  
11. <span data-ttu-id="e3ad7-146">Fügen Sie dem Berechnungsskript nach dem Befehl **Calculate;** und vor dem neu hinzugefügten Berechnungsskript eine neue Zeile hinzu, und geben Sie anschließend im Skript den folgenden Text in die gesonderte Zeile ein:</span><span class="sxs-lookup"><span data-stu-id="e3ad7-146">Add a new line in the calculation script after the **Calculate;** command and before the newly added calculation script, and then add the following text to the script on its own line:</span></span>  
  
    ```  
    /* Calculations to aggregate Internet Sales and Reseller Sales measures */  
    ```  
  
     <span data-ttu-id="e3ad7-147">Die folgende Abbildung stellt die Berechnungsskripts dar, wie sie im Bereich **Berechnungsausdrücke** zum jetzigen Zeitpunkt im Tutorial aussehen sollten.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-147">The following image shows the calculation scripts as they should appear in the **Calculation Expressions** pane at this point in the tutorial.</span></span>  
  
     <span data-ttu-id="e3ad7-148">![Skripts im Bereich für Berechnungsausdrücke](../../2014/tutorials/media/l6-calculatedmembers-04.gif "Skripts im Bereich für Berechnungsausdrücke")</span><span class="sxs-lookup"><span data-stu-id="e3ad7-148">![Scripts in Calculation Expressions pane](../../2014/tutorials/media/l6-calculatedmembers-04.gif "Scripts in Calculation Expressions pane")</span></span>  
  
12. <span data-ttu-id="e3ad7-149">Klicken Sie auf der Symbolleiste der Registerkarte **Berechnungen** auf **Formularansicht**, vergewissern Sie sich, dass `[Total Sales Amount]` im Bereich **Skript Planer** ausgewählt ist, und klicken Sie dann auf **Neues berechnetes**Element.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-149">On the toolbar of the **Calculations** tab, click **Form View**, verify that `[Total Sales Amount]` is selected in the **Script Organizer** pane, and then click **New Calculated Member**.</span></span>  
  
13. <span data-ttu-id="e3ad7-150">Ändern Sie den Namen des neuen berechneten Elements in `[Total Product Cost]` , und erstellen Sie dann den folgenden Ausdruck im Feld **Ausdruck** :</span><span class="sxs-lookup"><span data-stu-id="e3ad7-150">Change the name of this new calculated member to `[Total Product Cost]`, and then create the following expression in the **Expression** box:</span></span>  
  
    ```  
    [Measures].[Internet Sales-Total Product Cost] + [Measures].[Reseller Sales-Total Product Cost]  
    ```  
  
14. <span data-ttu-id="e3ad7-151">Wählen Sie in der Liste **Formatzeichenfolge** die Option **"Currency"** aus.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-151">In the **Format string** list, select **"Currency"**.</span></span>  
  
15. <span data-ttu-id="e3ad7-152">Aktivieren Sie in der Liste **Verhalten für nicht leere Elemente** die Kontrollkästchen für **Internet Sales-Total Product Cost** und **Reseller Sales-Total Product Cost**, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-152">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Total Product Cost** and **Reseller Sales-Total Product Cost**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e3ad7-153">Sie haben somit zwei berechnete Elemente definiert, die beide im Bereich **Skriptplaner** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-153">You have now defined two calculated members, both of which are visible in the **Script Organizer** pane.</span></span> <span data-ttu-id="e3ad7-154">Diese berechneten Elemente können von anderen Berechnungen verwendet werden, die Sie nachfolgend im Berechnungsskript definieren.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-154">These calculated members can be used by other calculations that you define later in the calculation script.</span></span> <span data-ttu-id="e3ad7-155">Die Definition aller berechneten Elemente kann durch Auswählen des berechneten Elements im Bereich **Skriptplaner** angezeigt werden. Die Definition des berechneten Elements wird im Bereich **Berechnungsausdrücke** in der Formularansicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-155">You can view the definition of any calculated member by selecting the calculated member in the **Script Organizer** pane; the definition of the calculated member will appear in the **Calculation Expressions** pane in the Form view.</span></span> <span data-ttu-id="e3ad7-156">Neu definierte berechnete Elemente werden erst nach dem Bereitstellen der Objekte im Bereich **Berechnungstools** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-156">Newly defined calculated members will not appear in the **Calculation Tools** pane until these objects have been deployed.</span></span> <span data-ttu-id="e3ad7-157">Berechnungen müssen nicht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-157">Calculations do not require processing.</span></span>  
  
## <a name="defining-gross-profit-margin-calculations"></a><span data-ttu-id="e3ad7-158">Definieren von Berechnungen zur Bruttorendite</span><span class="sxs-lookup"><span data-stu-id="e3ad7-158">Defining Gross Profit Margin Calculations</span></span>  
  
1.  <span data-ttu-id="e3ad7-159">Vergewissern Sie sich, dass `[Total Product Cost]` im Bereich **Skript Planer** ausgewählt ist, und klicken Sie dann auf der Symbolleiste der Registerkarte **Berechnungen** auf **Neues berechnetes** Element.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-159">Verify that `[Total Product Cost]` is selected in the **Script Organizer** pane, and then click **New Calculated Member** on the toolbar of the **Calculations** tab.</span></span>  
  
2.  <span data-ttu-id="e3ad7-160">Ändern Sie im Feld **Name** den Namen des neuen berechneten Measures in `[Internet GPM]` .</span><span class="sxs-lookup"><span data-stu-id="e3ad7-160">In the **Name** box, change the name of this new calculated measure to `[Internet GPM]`.</span></span>  
  
3.  <span data-ttu-id="e3ad7-161">Erstellen Sie im Feld **Ausdruck** den folgenden MDX-Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="e3ad7-161">In the **Expression** box, create the following MDX expression:</span></span>  
  
    ```  
    ([Measures].[Internet Sales-Sales Amount] -   
    [Measures].[Internet Sales-Total Product Cost]) /  
    [Measures].[Internet Sales-Sales Amount]  
    ```  
  
4.  <span data-ttu-id="e3ad7-162">Wählen Sie in der Liste **Formatzeichenfolge** die Option **"Percent"** aus.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-162">In the **Format string** list, select **"Percent"**.</span></span>  
  
5.  <span data-ttu-id="e3ad7-163">Aktivieren Sie in der Liste **Verhalten für nicht leere Elemente** das Kontrollkästchen für **Internet Sales-Sales Amount**, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-163">In the **Non-empty behavior** list, select the check box for **Internet Sales-Sales Amount**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="e3ad7-164">Klicken Sie auf der Symbolleiste der Registerkarte **Berechnungen** auf **Neues berechnetes Element**.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-164">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
7.  <span data-ttu-id="e3ad7-165">Ändern Sie im Feld **Name** den Namen des neuen berechneten Measures in `[Reseller GPM]` .</span><span class="sxs-lookup"><span data-stu-id="e3ad7-165">In the **Name** box, change the name of this new calculated measure to `[Reseller GPM]`.</span></span>  
  
8.  <span data-ttu-id="e3ad7-166">Erstellen Sie im Feld **Ausdruck** den folgenden MDX-Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="e3ad7-166">In the **Expression** box, create the following MDX expression:</span></span>  
  
    ```  
    ([Measures].[Reseller Sales-Sales Amount] -   
    [Measures].[Reseller Sales-Total Product Cost]) /  
    [Measures].[Reseller Sales-Sales Amount]  
    ```  
  
9. <span data-ttu-id="e3ad7-167">Wählen Sie in der Liste **Formatzeichenfolge** die Option **"Percent"** aus.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-167">In the **Format string** list, select **"Percent"**.</span></span>  
  
10. <span data-ttu-id="e3ad7-168">Aktivieren Sie in der Liste **Verhalten für nicht leere Elemente** das Kontrollkästchen für **Reseller Sales-Sales Amount**, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-168">In the **Non-empty behavior** list, select the check box for **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="e3ad7-169">Klicken Sie auf der Symbolleiste der Registerkarte **Berechnungen** auf **Neues berechnetes Element**.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-169">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
12. <span data-ttu-id="e3ad7-170">Ändern Sie im Feld **Name** den Namen dieses berechneten Measures in `[Total GPM]` .</span><span class="sxs-lookup"><span data-stu-id="e3ad7-170">In the **Name** box, change the name of this calculated measure to `[Total GPM]`.</span></span>  
  
13. <span data-ttu-id="e3ad7-171">Erstellen Sie im Feld **Ausdruck** den folgenden MDX-Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="e3ad7-171">In the **Expression** box, create the following MDX expression:</span></span>  
  
    ```  
    ([Measures].[Total Sales Amount] -   
    [Measures].[Total Product Cost]) /  
    [Measures].[Total Sales Amount]  
    ```  
  
     <span data-ttu-id="e3ad7-172">Dieses berechnete Element verweist auf andere berechnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-172">Notice that this calculated member is referencing other calculated members.</span></span> <span data-ttu-id="e3ad7-173">Da dieses berechnete Element erst nach den berechneten Elementen berechnet wird, auf die es verweist, ist dies ein gültiges berechnetes Element.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-173">Because this calculated member will be calculated after the calculated members that it references, this is a valid calculated member.</span></span>  
  
14. <span data-ttu-id="e3ad7-174">Wählen Sie in der Liste **Formatzeichenfolge** die Option **"Percent"** aus.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-174">In the **Format string** list, select **"Percent"**.</span></span>  
  
15. <span data-ttu-id="e3ad7-175">Aktivieren Sie in der Liste **Verhalten für nicht leere Elemente** die Kontrollkästchen für **Internet Sales-Sales Amount** und **Reseller Sales-Sales Amount**, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-175">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
16. <span data-ttu-id="e3ad7-176">Klicken Sie auf der Symbolleiste der Registerkarte **Berechnungen** auf **Skriptansicht** , und überprüfen Sie die drei Berechnungen, die gerade dem Berechnungsskript hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-176">On the toolbar of the **Calculations** tab, click **Script View** and review the three calculations you just added to the calculation script.</span></span>  
  
17. <span data-ttu-id="e3ad7-177">Fügen Sie dem Berechnungs Skript direkt vor der Berechnung eine neue Zeile hinzu `[Internet GPM]` , und fügen Sie dann den folgenden Text in der eigenen Zeile in das Skript ein:</span><span class="sxs-lookup"><span data-stu-id="e3ad7-177">Add a new line in the calculation script immediately before the `[Internet GPM]` calculation, and then add the following text to the script on its own line:</span></span>  
  
    ```  
    /* Calculations to calculate gross profit margin */  
    ```  
  
     <span data-ttu-id="e3ad7-178">Die folgende Abbildung stellt den Bereich **Ausdrücke** mit den drei neuen Berechnungen dar.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-178">The following image shows the **Expressions** pane with the three new calculations.</span></span>  
  
     <span data-ttu-id="e3ad7-179">![Neue Berechnungen im Bereich für Berechnungsausdrücke](../../2014/tutorials/media/l6-calculatedmembers-05.gif "Neue Berechnungen im Bereich für Berechnungsausdrücke")</span><span class="sxs-lookup"><span data-stu-id="e3ad7-179">![New calculations in Calculation Expressions pane](../../2014/tutorials/media/l6-calculatedmembers-05.gif "New calculations in Calculation Expressions pane")</span></span>  
  
## <a name="defining-the-percent-of-total-calculations"></a><span data-ttu-id="e3ad7-180">Definieren der Berechnungen zum Prozentsatz der Summe</span><span class="sxs-lookup"><span data-stu-id="e3ad7-180">Defining the Percent of Total Calculations</span></span>  
  
1.  <span data-ttu-id="e3ad7-181">Klicken Sie auf der Symbolleiste der Registerkarte **Berechnungen** auf **Formularansicht**.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-181">On the toolbar of the **Calculations** tab, click **Form View**.</span></span>  
  
2.  <span data-ttu-id="e3ad7-182">Wählen Sie im Bereich **Skript Planer** die Option `[Total GPM]` aus, und klicken Sie dann auf der Symbolleiste der Registerkarte **Berechnungen** auf **Neues berechnetes** Element.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-182">In the **Script Organizer** pane, select `[Total GPM]`, and then click **New Calculated Member** on the toolbar of the **Calculations** tab.</span></span>  
  
     <span data-ttu-id="e3ad7-183">Wenn Sie zuerst auf das letzte berechnete Element im Bereich **Skriptplaner** klicken, ehe Sie auf **Neues berechnetes Element** klicken, wird sichergestellt, dass das neue berechnete Element am Ende des Skripts eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-183">Clicking the final calculated member in the **Script Organizer** pane before you click **New Calculated Member** guarantees that the new calculated member will be entered at the end of the script.</span></span> <span data-ttu-id="e3ad7-184">Skripts werden in der Reihenfolge ausgeführt, in der sie im Bereich **Skriptplaner** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-184">Scripts execute in the order that they appear in the **Script Organizer** pane.</span></span>  
  
3.  <span data-ttu-id="e3ad7-185">Ändern Sie den Namen des neuen berechneten Elements in `[Internet Sales Ratio to All Products]` .</span><span class="sxs-lookup"><span data-stu-id="e3ad7-185">Change the name of this new calculated member to `[Internet Sales Ratio to All Products]`.</span></span>  
  
4.  <span data-ttu-id="e3ad7-186">Geben Sie den folgenden Ausdruck in das Feld **Ausdruck** ein:</span><span class="sxs-lookup"><span data-stu-id="e3ad7-186">Type the following expression in the **Expression** box:</span></span>  
  
    ```  
    Case  
        When IsEmpty( [Measures].[Internet Sales-Sales Amount] )   
        Then 0  
        Else ( [Product].[Product Categories].CurrentMember,  
               [Measures].[Internet Sales-Sales Amount]) /  
             ( [Product].[Product Categories].[(All)].[All],   
               [Measures].[Internet Sales-Sales Amount] )  
        End  
    ```  
  
     <span data-ttu-id="e3ad7-187">Dieser MDX-Ausdruck berechnet den Anteil an den gesamten Internetverkäufen der einzelnen Produkte.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-187">This MDX expression calculates the contribution to total Internet sales of each product.</span></span> <span data-ttu-id="e3ad7-188">Durch die Case-Anweisung in Kombination mit der IS EMPTY-Funktion wird sichergestellt, dass kein Fehler aufgrund einer Division durch Null auftritt, wenn ein Produkt keine Verkäufe aufweist.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-188">The Case statement together with the IS EMPTY function ensures that a divide by zero error does not occur when a product has no sales.</span></span>  
  
5.  <span data-ttu-id="e3ad7-189">Wählen Sie in der Liste **Formatzeichenfolge** die Option **"Percent"** aus.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-189">In the **Format string** list, select **"Percent"**.</span></span>  
  
6.  <span data-ttu-id="e3ad7-190">Aktivieren Sie in der Liste **Verhalten für nicht leere Elemente** das Kontrollkästchen für **Internet Sales-Sales Amount**, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-190">In the **Non-empty behavior** list, select the check box for **Internet Sales-Sales Amount**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="e3ad7-191">Klicken Sie auf der Symbolleiste der Registerkarte **Berechnungen** auf **Neues berechnetes Element**.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-191">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
8.  <span data-ttu-id="e3ad7-192">Ändern Sie den Namen dieses berechneten Elements in `[Reseller Sales Ratio to All Products]` .</span><span class="sxs-lookup"><span data-stu-id="e3ad7-192">Change the name of this calculated member to `[Reseller Sales Ratio to All Products]`.</span></span>  
  
9. <span data-ttu-id="e3ad7-193">Geben Sie den folgenden Ausdruck in das Feld **Ausdruck** ein:</span><span class="sxs-lookup"><span data-stu-id="e3ad7-193">Type the following expression in the **Expression** box:</span></span>  
  
    ```  
    Case  
        When IsEmpty( [Measures].[Reseller Sales-Sales Amount] )   
        Then 0  
        Else ( [Product].[Product Categories].CurrentMember,  
               [Measures].[Reseller Sales-Sales Amount]) /  
             ( [Product].[Product Categories].[(All)].[All],   
               [Measures].[Reseller Sales-Sales Amount] )  
        End  
    ```  
  
10. <span data-ttu-id="e3ad7-194">Wählen Sie in der Liste **Formatzeichenfolge** die Option **"Percent"** aus.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-194">In the **Format string** list, select **"Percent"**.</span></span>  
  
11. <span data-ttu-id="e3ad7-195">Aktivieren Sie in der Liste **Verhalten für nicht leere Elemente** das Kontrollkästchen für **Reseller Sales-Sales Amount**, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-195">In the **Non-empty behavior** list, select the check box for **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="e3ad7-196">Klicken Sie auf der Symbolleiste der Registerkarte **Berechnungen** auf **Neues berechnetes Element**.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-196">On the toolbar of the **Calculations** tab, click **New Calculated Member**.</span></span>  
  
13. <span data-ttu-id="e3ad7-197">Ändern Sie den Namen dieses berechneten Elements in `[Total Sales Ratio to All Products]` .</span><span class="sxs-lookup"><span data-stu-id="e3ad7-197">Change the name of this calculated member to `[Total Sales Ratio to All Products]`.</span></span>  
  
14. <span data-ttu-id="e3ad7-198">Geben Sie den folgenden Ausdruck in das Feld **Ausdruck** ein:</span><span class="sxs-lookup"><span data-stu-id="e3ad7-198">Type the following expression in the **Expression** box:</span></span>  
  
    ```  
    Case  
        When IsEmpty( [Measures].[Total Sales Amount] )   
        Then 0  
        Else ( [Product].[Product Categories].CurrentMember,  
               [Measures].[Total Sales Amount]) /  
             ( [Product].[Product Categories].[(All)].[All],   
               [Measures].[Total Sales Amount] )  
        End  
    ```  
  
15. <span data-ttu-id="e3ad7-199">Wählen Sie in der Liste **Formatzeichenfolge** die Option **"Percent"** aus.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-199">In the **Format string** list, select **"Percent"**.</span></span>  
  
16. <span data-ttu-id="e3ad7-200">Aktivieren Sie in der Liste **Verhalten für nicht leere Elemente** die Kontrollkästchen für **Internet Sales-Sales Amount** und **Reseller Sales-Sales Amount**, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-200">In the **Non-empty behavior** list, select the check boxes for **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount**, and then click **OK**.</span></span>  
  
17. <span data-ttu-id="e3ad7-201">Klicken Sie auf der Symbolleiste der Registerkarte **Berechnungen** auf **Skriptansicht**, und überprüfen Sie anschließend die drei Berechnungen, die gerade dem Berechnungsskript hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-201">On the toolbar of the **Calculations** tab, click **Script View**, and then review the three calculations that you just added to the calculation script.</span></span>  
  
18. <span data-ttu-id="e3ad7-202">Fügen Sie dem Berechnungs Skript direkt vor der Berechnung eine neue Zeile hinzu `[Internet Sales Ratio to All Products]` , und fügen Sie dann den folgenden Text in der eigenen Zeile in das Skript ein:</span><span class="sxs-lookup"><span data-stu-id="e3ad7-202">Add a new line in the calculation script immediately before the `[Internet Sales Ratio to All Products]` calculation, and then add the following text to the script on its own line:</span></span>  
  
    ```  
    /* Calculations to calculate percentage of product to total product sales */  
    ```  
  
     <span data-ttu-id="e3ad7-203">Sie haben nun insgesamt acht berechnete Elemente definiert, die im Bereich **Skriptplaner** angezeigt werden, falls Sie sich in der Formularansicht befinden.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-203">You have now defined a total of eight calculated members, which are visible in the **Script Organizer** pane when you are in Form view.</span></span>  
  
## <a name="browsing-the-new-calculated-members"></a><span data-ttu-id="e3ad7-204">Durchsuchen der neuen berechneten Elemente</span><span class="sxs-lookup"><span data-stu-id="e3ad7-204">Browsing the New Calculated Members</span></span>  
  
1.  <span data-ttu-id="e3ad7-205">Klicken Sie im Menü **Erstellen** von [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]auf **Analysis Services Tutorial bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-205">On the **Build** menu of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click **Deploy Analysis Services Tutorial**.</span></span>  
  
2.  <span data-ttu-id="e3ad7-206">Wechseln Sie nach erfolgreichem Abschluss der Bereitstellung zur Registerkarte **Browser** , und klicken Sie auf **Verbindung wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-206">When deployment has successfully completed, switch to the **Browser** tab, click **Reconnect**.</span></span>  
  
3.  <span data-ttu-id="e3ad7-207">Klicken Sie auf das Excel-Symbol und anschließend auf **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-207">Click the Excel icon, and then click **Enable**.</span></span>  
  
4.  <span data-ttu-id="e3ad7-208">Erweitern Sie im Bereich **PivotTable-Feldliste** den Ordner **Werte** , um die neuen berechneten Elemente in der Measures-Dimension anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-208">In the **PivotTable Field List** pane, expand **Values** folder to view the new calculated members in the Measures dimension.</span></span>  
  
5.  <span data-ttu-id="e3ad7-209">Ziehen Sie **Total Sales Amount** in den Bereich Werte, und überprüfen Sie anschließend die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-209">Drag the **Total Sales Amount** to the Values area, and then review the results.</span></span>  
  
     <span data-ttu-id="e3ad7-210">Ziehen Sie das **Internet Sales-Sales Amount** -Measure und das **Reseller Sales-Sales Amount** -Measure aus der **Internet Sales** -Measuregruppe und der **Reseller Sales** -Measuregruppe in den Bereich Werte.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-210">Drag **Internet Sales-Sales Amount** and **Reseller Sales-Sales Amount** measures from the **Internet Sales** and **Reseller Sales** measure groups to the Values area.</span></span>  
  
     <span data-ttu-id="e3ad7-211">Das **Total Sales Amount** -Measure ist die Summe aus dem **Internet Sales-Sales Amount** -Measure und dem **Reseller Sales-Sales Amount** -Measure.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-211">Notice that the **Total Sales Amount** measure is the sum of the **Internet Sales-Sales Amount** measure and the **Reseller Sales-Sales Amount** measure.</span></span>  
  
6.  <span data-ttu-id="e3ad7-212">Fügen Sie dem Filterbereich des Bereichs **Berichtsfilter** die benutzerdefinierte Hierarchie **Product Categories** hinzu, und filtern Sie die Daten anschließend nach **Mountain Bikes**.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-212">Add the **Product Categories** user-defined hierarchy to the filter area of the **Report Filter** area, and then filter the data by **Mountain Bikes**.</span></span>  
  
     <span data-ttu-id="e3ad7-213">Das **Total Sales Amount** -Measure wird für die **Mountain Bikes** -Kategorie der Produktverkäufe auf der Grundlage der Measures **Internet Sales-Sales Amount** und **Reseller Sales-Sales Amount** für **Mountain Bikes**berechnet.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-213">Notice that the **Total Sales Amount** measure is calculated for the **Mountain Bikes** category of product sales based on the **Internet Sales-Sales Amount** and the **Reseller Sales-Sales Amount** measures for **Mountain Bikes**.</span></span>  
  
7.  <span data-ttu-id="e3ad7-214">Fügen Sie dem Bereich **Zeilenbezeichnungen** die benutzerdefinierte Hierarchie „Date.Calendar Date“ hinzu, und überprüfen Sie anschließend die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-214">Add the **Date.Calendar Date** user-defined hierarchy to the Row labels area, and then review the results.</span></span>  
  
     <span data-ttu-id="e3ad7-215">Das **Total Sales Amount** -Measure für jedes Kalenderjahr wird für die **Mountain Bikes** -Kategorie der Produktverkäufe auf der Grundlage der Measures **Internet Sales-Sales Amount** und **Reseller Sales-Sales Amount** für **Mountain Bikes**berechnet.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-215">Notice that the **Total Sales Amount** measure for each calendar year is calculated for the **Mountain Bikes** category of product sales based on the **Internet Sales-Sales Amount** and the **Reseller Sales-Sales Amount** measures for **Mountain Bikes**.</span></span>  
  
8.  <span data-ttu-id="e3ad7-216">Fügen Sie dem Bereich „Werte“ die Measures **Total GPM**die Measures **Internet GPM**, **Reseller GPM** hinzu, und überprüfen Sie anschließend die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-216">Add the **Total GPM**, **Internet GPM**, and **Reseller GPM** measures to the Values area, and then review the results.</span></span>  
  
     <span data-ttu-id="e3ad7-217">Die Bruttorendite für Verkäufe des Wiederverkäufers ist deutlich niedriger als für Verkäufe über das Internet, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-217">Notice that the gross profit margin for reseller sales is significantly lower than for sales over the Internet, as shown in the following image.</span></span>  
  
     <span data-ttu-id="e3ad7-218">![Datenbereich mit Verkäufen des Wiederverkäufers](../../2014/tutorials/media/l6-calculatedmembers-7b.gif "Datenbereich mit Verkäufen des Wiederverkäufers")</span><span class="sxs-lookup"><span data-stu-id="e3ad7-218">![Data pane showing reseller sales](../../2014/tutorials/media/l6-calculatedmembers-7b.gif "Data pane showing reseller sales")</span></span>  
  
9. <span data-ttu-id="e3ad7-219">Fügen Sie dem Bereich „Werte“ die Measures **Total Sales Ratio to All Products**, **Internet Sales Ratio to All Products**und **Reseller Sales Ratio to All Products** hinzu.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-219">Add the **Total Sales Ratio to All Products**, **Internet Sales Ratio to All Products**, and **Reseller Sales Ratio to All Products** measures to the Values area.</span></span>  
  
     <span data-ttu-id="e3ad7-220">Das Verhältnis zwischen den Verkäufen von Mountainbikes und allen Produkten ist bei den Internetverkäufen im Laufe der Zeit gestiegen, bei den Verkäufen durch Wiederverkäufer jedoch gesunken.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-220">Notice that the ratio of the sales of mountain bikes to all products has increased over time for Internet sales, but is decreasing over time for reseller sales.</span></span> <span data-ttu-id="e3ad7-221">Darüber hinaus ist das Verhältnis zwischen den Verkäufen von Mountainbikes und allen Produkten bei Verkäufen über Wiederverkäufer niedriger als bei Verkäufen über das Internet.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-221">Notice also that the ratio of the sale of mountain bikes to all products is lower from sales through resellers than it is for sales over the Internet.</span></span>  
  
10. <span data-ttu-id="e3ad7-222">Wechseln Sie den Filter von **Mountain Bikes** zu **Bikes**, und überprüfen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-222">Change the filter from **Mountain Bikes** to **Bikes**, and review the results.</span></span>  
  
     <span data-ttu-id="e3ad7-223">Die Bruttorendite für alle durch Wiederverkäufer verkauften Fahrräder ist negativ, da Tourenräder und Straßenräder mit Verlust verkauft werden.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-223">Notice that the gross profit margin for all bikes sold through resellers is negative, because touring bikes and road bikes are being sold at a loss.</span></span>  
  
11. <span data-ttu-id="e3ad7-224">Wechseln Sie den Filter zu **Accessories**, und überprüfen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-224">Change the filter to **Accessories**, and then review the results.</span></span>  
  
     <span data-ttu-id="e3ad7-225">Die Verkaufszahlen für das Zubehör steigen im Laufe der Zeit, doch machen diese Verkäufe nur einen Bruchteil der Gesamtverkäufe aus.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-225">Notice that the sale of accessories is increasing over time, but that these sales make up only a small fraction of total sales.</span></span> <span data-ttu-id="e3ad7-226">Die Bruttorendite beim Verkauf von Zubehör ist jedoch höher als beim Verkauf von Fahrrädern.</span><span class="sxs-lookup"><span data-stu-id="e3ad7-226">Notice also that the gross profit margin for sales of accessories is higher than for bikes.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="e3ad7-227">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="e3ad7-227">Next Task in Lesson</span></span>  
 [<span data-ttu-id="e3ad7-228">Definieren von benannten Mengen</span><span class="sxs-lookup"><span data-stu-id="e3ad7-228">Defining Named Sets</span></span>](lesson-6-2-defining-named-sets.md)  
  
## <a name="see-also"></a><span data-ttu-id="e3ad7-229">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e3ad7-229">See Also</span></span>  
 <span data-ttu-id="e3ad7-230">[Einbeziehen](multidimensional-models-olap-logical-cube-objects/calculations.md) </span><span class="sxs-lookup"><span data-stu-id="e3ad7-230">[Calculations](multidimensional-models-olap-logical-cube-objects/calculations.md) </span></span>  
 <span data-ttu-id="e3ad7-231">[Berechnungen in mehrdimensionalen Modellen](multidimensional-models/calculations-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="e3ad7-231">[Calculations in Multidimensional Models](multidimensional-models/calculations-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="e3ad7-232">Erstellen von berechneten Elementen</span><span class="sxs-lookup"><span data-stu-id="e3ad7-232">Create Calculated Members</span></span>](multidimensional-models/create-calculated-members.md)  
  
  
