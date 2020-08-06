---
title: Festlegen der Eigenschaften einer Rang folgen Einschränkung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Precedence Constraint Editor dialog box
- precedence constraints [Integration Services], properties
ms.assetid: d990f600-5c09-4cd5-8528-0a58d79dc9f2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 55b95bdb79d801156bef6198bc0f57accb5d9517
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621572"
---
# <a name="set-the-properties-of-a-precedence-constraint"></a><span data-ttu-id="51f56-102">Festlegen der Eigenschaften von Rangfolgeneinschränkungen</span><span class="sxs-lookup"><span data-stu-id="51f56-102">Set the Properties of a Precedence Constraint</span></span>
  <span data-ttu-id="51f56-103">Um Eigenschaften für Rangfolgeneinschränkungen festzulegen, verwenden Sie eines der folgenden Tools:</span><span class="sxs-lookup"><span data-stu-id="51f56-103">To set properties on precedence constraints, you can use one of these tools:</span></span>  
  
-   <span data-ttu-id="51f56-104">Sie können das Dialogfeld **Rangfolgeneinschränkungs-Editor** verwenden.</span><span class="sxs-lookup"><span data-stu-id="51f56-104">You can use the **Precedence Constraint Editor** dialog box.</span></span>  
  
-   <span data-ttu-id="51f56-105">Sie können das Eigenschaftenfenster verwenden.</span><span class="sxs-lookup"><span data-stu-id="51f56-105">You can use the Properties window.</span></span> <span data-ttu-id="51f56-106">Im Eigenschaftenfenster werden Eigenschaften zum Konfigurieren von Rangfolgeneinschränkungen aufgelistet, die nicht im Dialogfeld **Rangfolgeneinschränkungs-Editor** verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="51f56-106">The Properties window lists properties for configuring precedence constraints that are not available in the **Precedence Constraint Editor** dialog box.</span></span> <span data-ttu-id="51f56-107">Im Eigenschaftenfenster können Sie eine Beschreibung und einen Namen der Rangfolgeneinschränkung bereitstellen und die Anmerkung konfigurieren, um die Rangfolgeneinschränkung auf der Entwurfsoberfläche anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="51f56-107">In the Properties window, you can provide a description and name of the precedence constraint, and configure the annotation to display for the precedence constraint on the design surface.</span></span>  
  
 <span data-ttu-id="51f56-108">Im folgenden Verfahren wird das Festlegen der Eigenschaften von Rangfolgeneinschränkungen mithilfe der einzelnen Tools beschrieben.</span><span class="sxs-lookup"><span data-stu-id="51f56-108">The following procedures describe how to set properties on precedence constraints by using each of these tools.</span></span>  
  
### <a name="to-set-the-properties-of-a-precedence-constraint-by-using-the-precedence-constraint-editor"></a><span data-ttu-id="51f56-109">So legen Sie die Eigenschaften von Rangfolgeneinschränkungen mithilfe des Rangfolgeneinschränkungs-Editors fest</span><span class="sxs-lookup"><span data-stu-id="51f56-109">To set the properties of a precedence constraint by using the Precedence Constraint Editor</span></span>  
  
1.  <span data-ttu-id="51f56-110">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="51f56-110">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="51f56-111">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="51f56-111">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="51f56-112">Klicken Sie auf die Registerkarte **Ablaufsteuerung** .</span><span class="sxs-lookup"><span data-stu-id="51f56-112">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="51f56-113">Doppelklicken Sie auf die Rangfolgeneinschränkung.</span><span class="sxs-lookup"><span data-stu-id="51f56-113">Double-click the precedence constraint.</span></span>  
  
     <span data-ttu-id="51f56-114">Das Dialogfeld **Rangfolgeneinschränkungs-Editor** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="51f56-114">The **Precedence Constraint Editor** opens.</span></span>  
  
5.  <span data-ttu-id="51f56-115">Wählen Sie in der Dropdownliste **Auswertungsvorgang** einen Auswertungsvorgang aus.</span><span class="sxs-lookup"><span data-stu-id="51f56-115">In the **Evaluation operation** drop-down list, select an evaluation operation.</span></span>  
  
6.  <span data-ttu-id="51f56-116">`Value`Wählen Sie in der Dropdown Liste das Ausführungs Ergebnis der ausführbaren Datei der Rangfolge aus.</span><span class="sxs-lookup"><span data-stu-id="51f56-116">In the `Value` drop-down list, select the execution result of the precedence executable.</span></span>  
  
7.  <span data-ttu-id="51f56-117">Wenn der Auswertungs Vorgang einen Ausdruck verwendet, `Expression` Geben Sie im Feld einen Ausdruck ein, und klicken Sie auf **Testen** , um den Ausdruck auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="51f56-117">If the evaluation operation uses an expression, in the `Expression` box, type an expression, and click **Test** to evaluate the expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="51f56-118">Bei Variablennamen wird nach Groß-/Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="51f56-118">Variable names are case-sensitive.</span></span>  
  
8.  <span data-ttu-id="51f56-119">Wenn mehrere Tasks oder Container mit der eingeschränkten ausführbaren Datei verbunden sind, wählen Sie **logisch und** aus, um anzugeben, dass die Ausführungs Ergebnisse aller vorherigen ausführbaren Dateien als ausgewertet werden müssen `true` .</span><span class="sxs-lookup"><span data-stu-id="51f56-119">If multiple tasks or containers are connected to the constrained executable, select **Logical AND** to specify that the execution results of all preceding executables must evaluate to `true`.</span></span> <span data-ttu-id="51f56-120">Wählen Sie **logisches OR** aus, um anzugeben, dass nur ein Ausführungs Ergebnis als ausgewertet werden muss `true` .</span><span class="sxs-lookup"><span data-stu-id="51f56-120">Select **Logical OR** to specify that only one execution result must evaluate to `true`.</span></span>  
  
9. <span data-ttu-id="51f56-121">Klicken Sie auf **OK** , um das Dialogfeld **Rangfolgeneinschränkungs-Editor**zu schließen.</span><span class="sxs-lookup"><span data-stu-id="51f56-121">Click **OK** to close the **Precedence Constraint Editor**.</span></span>  
  
10. <span data-ttu-id="51f56-122">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="51f56-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-set-the-properties-of-a-precedence-constraint-by-using-the-properties-window"></a><span data-ttu-id="51f56-123">So legen Sie die Eigenschaften von Rangfolgeneinschränkungen mithilfe des Eigenschaftenfensters fest</span><span class="sxs-lookup"><span data-stu-id="51f56-123">To set the properties of a precedence constraint by using the Properties window</span></span>  
  
1.  <span data-ttu-id="51f56-124">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt mit dem Paket, das Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="51f56-124">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to modify.</span></span>  
  
2.  <span data-ttu-id="51f56-125">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="51f56-125">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="51f56-126">Klicken Sie auf die Registerkarte **Ablauf Steuerung** . Klicken Sie in der Entwurfs Oberfläche der Registerkarte **Ablauf Steuerung** mit der rechten Maustaste auf die Rang folgen Einschränkung, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="51f56-126">Click the **Control Flow** tab. On the design surface of the **Control Flow** tab, right-click the precedence constraint, and then click **Properties**.</span></span> <span data-ttu-id="51f56-127">Ändern Sie im Fenster Eigenschaften die Eigenschaftswerte.</span><span class="sxs-lookup"><span data-stu-id="51f56-127">In the Properties window, modify the property values.</span></span>  
  
4.  <span data-ttu-id="51f56-128">Legen Sie im Fenster **Eigenschaften** die folgenden Lese-/Schreibeigenschaften der Rangfolgeneinschränkung fest:</span><span class="sxs-lookup"><span data-stu-id="51f56-128">In the **Properties** window, set the following read/write properties of precedence constraints:</span></span>  
  
    |<span data-ttu-id="51f56-129">Lese/Schreibeigenschaft</span><span class="sxs-lookup"><span data-stu-id="51f56-129">Read/write property</span></span>|<span data-ttu-id="51f56-130">Konfigurationsaktion</span><span class="sxs-lookup"><span data-stu-id="51f56-130">Configuration action</span></span>|  
    |--------------------------|--------------------------|  
    |<span data-ttu-id="51f56-131">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="51f56-131">Description</span></span>|<span data-ttu-id="51f56-132">Bereitstellen einer Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="51f56-132">Provide a description.</span></span>|  
    |<span data-ttu-id="51f56-133">EvalOp</span><span class="sxs-lookup"><span data-stu-id="51f56-133">EvalOp</span></span>|<span data-ttu-id="51f56-134">Auswählen eines Auswertungsvorgangs.</span><span class="sxs-lookup"><span data-stu-id="51f56-134">Select an evaluation operation.</span></span> <span data-ttu-id="51f56-135">Wenn die Vorgänge `Expression` , **ExpressionAndConstant**oder **ExpressionOrConstant** ausgewählt sind, können Sie einen Ausdruck angeben.</span><span class="sxs-lookup"><span data-stu-id="51f56-135">If the `Expression`, **ExpressionAndConstant**, or **ExpressionOrConstant** operation is selected, you can specify an expression.</span></span>|  
    |<span data-ttu-id="51f56-136">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="51f56-136">Expression</span></span>|<span data-ttu-id="51f56-137">Wenn der Auswertungsvorgang einen Ausdruck einschließt, wird ein Ausdruck bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="51f56-137">If the evaluation operation includes and expression, provide an expression.</span></span> <span data-ttu-id="51f56-138">Der Ausdruck muss zu einem booleschen Wert ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="51f56-138">The expression must evaluate to a Boolean.</span></span> <span data-ttu-id="51f56-139">Weitere Informationen zur Ausdruckssprache finden Sie unter [Integration Services-Ausdrücke &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="51f56-139">For more information about the expression language, see [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md).</span></span>|  
    |<span data-ttu-id="51f56-140">LogicalAnd</span><span class="sxs-lookup"><span data-stu-id="51f56-140">LogicalAnd</span></span>|<span data-ttu-id="51f56-141">Legen `LogicalAnd` Sie fest, um anzugeben, ob die Rang folgen Einschränkung zusammen mit anderen Rang folgen Einschränkungen ausgewertet wird, wenn mehrere ausführbare Dateien vorausgehen und mit der eingeschränkten ausführbaren Datei verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="51f56-141">Set `LogicalAnd` to specify whether the precedence constraint is evaluated in concert with other precedence constraints, when multiple executables precede and are linked to the constrained executable</span></span>|  
    |<span data-ttu-id="51f56-142">Name</span><span class="sxs-lookup"><span data-stu-id="51f56-142">Name</span></span>|<span data-ttu-id="51f56-143">Aktualisieren des Namens der Rangfolgeneinschränkung.</span><span class="sxs-lookup"><span data-stu-id="51f56-143">Update the name of the precedence constraint.</span></span>|  
    |<span data-ttu-id="51f56-144">ShowAnnotation</span><span class="sxs-lookup"><span data-stu-id="51f56-144">ShowAnnotation</span></span>|<span data-ttu-id="51f56-145">Geben Sie den Typ der zu verwendenden Anmerkung ein.</span><span class="sxs-lookup"><span data-stu-id="51f56-145">Specify the type of annotation to use.</span></span> <span data-ttu-id="51f56-146">Wählen Sie **Never** aus, um Anmerkungen zu deaktivieren, **AsNeeded** , um Anmerkungen bei Bedarf zu aktivieren, **ConstraintName** , um automatisch den Wert mithilfe der Name-Eigenschaft anzumerken, **ConstraintDescription** , um automatisch den Wert mithilfe der Description-Eigenschaft anzumerken, und **ConstraintOptions** , um automatisch den Wert mithilfe der Eigenschaften Value und Expression anzumerken.</span><span class="sxs-lookup"><span data-stu-id="51f56-146">Choose **Never** to disable annotations, **AsNeeded** to enable annotation on demand, **ConstraintName** to automatically annotate using the value of the Name property, **ConstraintDescription** to automatically annotate using the value of the Description property, and **ConstraintOptions** to automatically annotate using the values of the Value and Expression properties.</span></span>|  
    |<span data-ttu-id="51f56-147">Wert</span><span class="sxs-lookup"><span data-stu-id="51f56-147">Value</span></span>|<span data-ttu-id="51f56-148">Wenn der Auswertungsvorgang in der EvalOP-Eigenschaft eine Einschränkung enthält, wählen Sie das Ausführungsergebnis der eingeschränkten ausführbaren Datei aus.</span><span class="sxs-lookup"><span data-stu-id="51f56-148">If the evaluation operation specified in the EvalOP property includes a constraint, select the execution result of the constraining executable.</span></span>|  
  
5.  <span data-ttu-id="51f56-149">Schließen Sie das Fenster Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="51f56-149">Close the Properties window.</span></span>  
  
6.  <span data-ttu-id="51f56-150">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="51f56-150">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51f56-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51f56-151">See Also</span></span>  
 <span data-ttu-id="51f56-152">[Rang folgen Einschränkungen](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="51f56-152">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="51f56-153">[Verbinden von Tasks und Containern mithilfe einer Standard Rang folgen Einschränkung](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="51f56-153">[Connect Tasks and Containers by Using a Default Precedence Constraint](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span></span>  
 <span data-ttu-id="51f56-154">[Festlegen des Werts einer Rang folgen Einschränkung mithilfe des Kontextmenüs](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span><span class="sxs-lookup"><span data-stu-id="51f56-154">[Set the Value of a Precedence Constraint by Using the Shortcut Menu](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span></span>  
 [<span data-ttu-id="51f56-155">Verwenden eines Ausdrucks in einer Rangfolgeneinschränkung</span><span class="sxs-lookup"><span data-stu-id="51f56-155">Use an Expression in a Precedence Constraint</span></span>](../../2014/integration-services/use-an-expression-in-a-precedence-constraint.md)  
  
  
