---
title: Festlegen der Eigenschaften einer benutzerdefinierten Variablen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- modifying variables
- variables [Integration Services], properties
ms.assetid: f98ddbec-f668-4dba-a768-44ac3ae0536f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bf53be469e3d377f7efb379f78e85e31b26767b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726057"
---
# <a name="set-the-properties-of-a-user-defined-variable"></a><span data-ttu-id="d2a20-102">Festlegen der Eigenschaften von benutzerdefinierten Variablen</span><span class="sxs-lookup"><span data-stu-id="d2a20-102">Set the Properties of a User-Defined Variable</span></span>
  <span data-ttu-id="d2a20-103">Sie können eine der folgenden Funktionen verwenden, um die Eigenschaften einer benutzerdefinierten Variable in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]festzulegen:</span><span class="sxs-lookup"><span data-stu-id="d2a20-103">To set the properties of a user-defined variable in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], you can use one of the following features:</span></span>  
  
-   <span data-ttu-id="d2a20-104">Fenster "Variablen".</span><span class="sxs-lookup"><span data-stu-id="d2a20-104">Variables window.</span></span>  
  
-   <span data-ttu-id="d2a20-105">Eigenschaftenfenster.</span><span class="sxs-lookup"><span data-stu-id="d2a20-105">Properties window.</span></span> <span data-ttu-id="d2a20-106">Im Fenster **Eigenschaften** werden die Eigenschaften zum Konfigurieren von Variablen aufgelistet, die im Fenster **Variablen** nicht zur Verfügung stehen: Description, EvaluateAsExpression, Expression, ReadOnly, ValueType und IncludeInDebugDump.</span><span class="sxs-lookup"><span data-stu-id="d2a20-106">The **Properties** window lists properties for configuring variables that are not available in the **Variables** window: Description, EvaluateAsExpression, Expression, ReadOnly, ValueType, and IncludeInDebugDump.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="d2a20-107">stellt außerdem eine Gruppe von Systemvariablen bereit, deren Eigenschaften, mit Ausnahme der RaiseChangedEvent-Eigenschaft, nicht aktualisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="d2a20-107">also provides a set of system variables whose properties cannot be updated, with the exception of the RaiseChangedEvent property.</span></span>  
  
 <span data-ttu-id="d2a20-108">**Festlegen von Ausdrücken für Variablen**</span><span class="sxs-lookup"><span data-stu-id="d2a20-108">**Setting Expressions on Variables**</span></span>  
  
 <span data-ttu-id="d2a20-109">Wenn Sie das Fenster **Eigenschaften** verwenden, um Ausdrücke für eine benutzerdefinierte Variable festzulegen:</span><span class="sxs-lookup"><span data-stu-id="d2a20-109">When you use the **Properties** window to set expressions on a user-defined variable:</span></span>  
  
-   <span data-ttu-id="d2a20-110">Der Wert dieser Variablen kann durch die Value-Eigenschaft oder die Expression-Eigenschaft festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="d2a20-110">The value of a variable can be set by the Value or the Expression property.</span></span> <span data-ttu-id="d2a20-111">Standardmäßig ist die EvaluateAsExpression-Eigenschaft auf festgelegt, `False` und der Wert der Variablen wird durch die Value-Eigenschaft festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d2a20-111">By default, the EvaluateAsExpression property is set to `False` and the value of the variable is set by the Value property.</span></span> <span data-ttu-id="d2a20-112">Wenn Sie einen Ausdruck verwenden möchten, um den Wert festzulegen, müssen Sie zuerst EvaluateAsExpression auf festlegen `True` und dann einen Ausdruck in der Expression-Eigenschaft angeben.</span><span class="sxs-lookup"><span data-stu-id="d2a20-112">To use an expression to set the value, you must first set EvaluateAsExpression to `True`, and then provide an expression in the Expression property.</span></span> <span data-ttu-id="d2a20-113">Die Value-Eigenschaft wird automatisch auf das Auswertungsergebnis des Ausdrucks festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d2a20-113">The Value property is automatically set to the evaluation result of the expression.</span></span>  
  
-   <span data-ttu-id="d2a20-114">Die ValueType-Eigenschaft enthält den Datentyp des Werts in der Value-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d2a20-114">The ValueType property contains the data type of the value in the Value property.</span></span> <span data-ttu-id="d2a20-115">Wenn Value durch einen Ausdruck festgelegt wird, dann wird ValueType automatisch auf einen Datentyp aktualisiert, der mit dem Auswertungsergebnis des Ausdrucks kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="d2a20-115">When Value is set by an expression, ValueType is automatically updated to a data type that is compatible with the evaluation result of the expression.</span></span> <span data-ttu-id="d2a20-116">Wenn der Wert z. b. 0 und die ValueType-Eigenschaft **Int32** enthält und Sie dann Expression auf GETDATE () festlegen, enthält Value das aktuelle Datum und die aktuelle Uhrzeit, und ValueType ist auf festgelegt `DateTime` .</span><span class="sxs-lookup"><span data-stu-id="d2a20-116">For example, if Value contains 0 and ValueType property contains **Int32** and you then set Expression to GETDATE(), Value contains the current date and time and ValueType is set to `DateTime`.</span></span>  
  
-   <span data-ttu-id="d2a20-117">Das \*\* Eigenschaftenfenster\*\* für die Variable stellt den Zugriff auf das Dialogfeld **Ausdrucks-Generator** bereit.</span><span class="sxs-lookup"><span data-stu-id="d2a20-117">The **Properties** window for the variable provides access to the **Expression Builder** dialog box.</span></span> <span data-ttu-id="d2a20-118">Sie können dieses Tool zum Erstellen, Überprüfen und Auswerten von Ausdrücken verwenden.</span><span class="sxs-lookup"><span data-stu-id="d2a20-118">You can use this tool to build, validate, and evaluate expressions.</span></span> <span data-ttu-id="d2a20-119">Weitere Informationen finden Sie unter [Ausdrucks-Generator](expressions/expression-builder.md) und [Integration Services-Ausdrücke &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="d2a20-119">For more information, see [Expression Builder](expressions/expression-builder.md) and [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md).</span></span>  
  
 <span data-ttu-id="d2a20-120">Wenn Sie das Fenster **Variablen** verwenden, um Ausdrücke für eine benutzerdefinierte Variable festzulegen:</span><span class="sxs-lookup"><span data-stu-id="d2a20-120">When you use the **Variables** window to set expressions on a user-defined variable:</span></span>  
  
-   <span data-ttu-id="d2a20-121">Um einen Ausdruck zum Festlegen des Variablen Werts zu verwenden, vergewissern Sie sich zunächst, dass der Datentyp der Variablen mit dem Auswertungs Ergebnis des Ausdrucks kompatibel ist, und stellen Sie dann einen Ausdruck in der- `Expression` Spalte des **Variablen** Fensters bereit.</span><span class="sxs-lookup"><span data-stu-id="d2a20-121">To use an expression to set the variable value, first confirm that the variable data type is compatible with the evaluation result of the expression and then provide an expression in the `Expression` column of the **Variables** window.</span></span> <span data-ttu-id="d2a20-122">Die EvaluateAsExpression-Eigenschaft im **Eigenschaften** Fenster wird automatisch auf festgelegt `True` .</span><span class="sxs-lookup"><span data-stu-id="d2a20-122">The EvaluateAsExpression property in the **Properties** window is automatically set to `True`.</span></span>  
  
-   <span data-ttu-id="d2a20-123">Wenn Sie einer Variablen einen Ausdruck zuweisen, wird ein spezieller Symbolmarker neben der Variablen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d2a20-123">When you assign an expression to a variable, a special icon marker displays next to the variable.</span></span> <span data-ttu-id="d2a20-124">Dieser spezielle Symbolmarker wird auch neben Verbindungs-Managern und Tasks angezeigt, für die Ausdrücke festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="d2a20-124">This special icon marker also displays next to connection managers and tasks that have expressions set on them.</span></span>  
  
-   <span data-ttu-id="d2a20-125">Das Fenster **Variablen** für die Variable stellt den Zugriff auf das Dialogfeld **Ausdrucks-Generator** bereit.</span><span class="sxs-lookup"><span data-stu-id="d2a20-125">The **Variables** window for the variable provides access to the **Expression Builder** dialog box.</span></span> <span data-ttu-id="d2a20-126">Sie können dieses Tool zum Erstellen, Überprüfen und Auswerten von Ausdrücken verwenden.</span><span class="sxs-lookup"><span data-stu-id="d2a20-126">You can use this tool to build, validate, and evaluate expressions.</span></span> <span data-ttu-id="d2a20-127">Weitere Informationen finden Sie unter [Ausdrucks-Generator](expressions/expression-builder.md) und [Integration Services-Ausdrücke &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="d2a20-127">For more information, see [Expression Builder](expressions/expression-builder.md) and [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md).</span></span>  
  
 <span data-ttu-id="d2a20-128">Wenn Sie der Variablen im Fenster **Variablen** und **Eigenschaften** einen Ausdruck zuweisen und `EvaluateAsExpression` auf festgelegt ist `True` , können Sie den Datentyp der Variablen nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="d2a20-128">In both the **Variables** and **Properties** window, if you assign an expression to the variable, and `EvaluateAsExpression` is set to `True`, you cannot change the variable data type.</span></span>  
  
 <span data-ttu-id="d2a20-129">**Festlegen des Namespaces und der Namenseigenschaften**</span><span class="sxs-lookup"><span data-stu-id="d2a20-129">**Setting the Namespace and Name Properties**</span></span>  
  
 <span data-ttu-id="d2a20-130">Die Werte der Eigenschaften `Name` und `Namespace` müssen mit einem Buchstaben beginnen, wie in Unicode-Standard 2.0 definiert ist, oder mit einem Unterstrich (_).</span><span class="sxs-lookup"><span data-stu-id="d2a20-130">The values of the `Name` and `Namespace` properties must begin with an alphabetic character letter as defined by the Unicode Standard 2.0, or an underscore (_).</span></span> <span data-ttu-id="d2a20-131">Bei den nachfolgenden Zeichen kann es sich um Buchstaben oder Zahlen gemäß Unicode-Standard 2.0 oder um einem Unterstrich (\_) handeln.</span><span class="sxs-lookup"><span data-stu-id="d2a20-131">Subsequent characters can be letters or numbers as defined in the Unicode Standard 2.0, or the underscore (\_).</span></span>  
  
## <a name="using-the-variables-window-to-set-properties"></a><span data-ttu-id="d2a20-132">Verwenden des Variablenfensters zum Festlegen von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d2a20-132">Using the Variables Window to Set Properties</span></span>  
  
#### <a name="to-set-the-properties-of-a-variable-by-using-the-variables-window"></a><span data-ttu-id="d2a20-133">So legen Sie die Eigenschaften einer Variablen mithilfe des Variablenfensters fest</span><span class="sxs-lookup"><span data-stu-id="d2a20-133">To set the properties of a variable by using the Variables window</span></span>  
  
1.  <span data-ttu-id="d2a20-134">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="d2a20-134">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="d2a20-135">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d2a20-135">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="d2a20-136">Klicken Sie im Menü **SSIS** auf **Variablen**.</span><span class="sxs-lookup"><span data-stu-id="d2a20-136">On the **SSIS** menu, click **Variables**.</span></span>  
  
     <span data-ttu-id="d2a20-137">Sie können das Fenster **Variablen** auch anzeigen, indem Sie im Dialogfeld **Optionen** auf der Seite **Tastatur** den Befehl View.Variables einer beliebigen Tastenkombination zuordnen.</span><span class="sxs-lookup"><span data-stu-id="d2a20-137">You can optionally display the **Variables** window by mapping the View.Variables command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
4.  <span data-ttu-id="d2a20-138">Klicken Sie optional im Fenster **Variablen** auf **Rasteroptionen**, und wählen Sie die Spalten aus, die im Fenster **Variablen** angezeigt werden sollen. Wählen Sie dann die Filter aus, die auf die Liste der Variablen angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d2a20-138">Optionally, in the **Variables** window click **Grid Options**, and then select the columns to appear in the **Variables** window and select the filters to apply to the list of variables.</span></span>  
  
5.  <span data-ttu-id="d2a20-139">Wählen Sie die Variable in der Liste aus, und aktualisieren Sie dann die Werte in den `Name` **Datentypen**,,, und ändern Sie das `Value` `Namespace` **Änderungs Ereignis**, die **Beschreibung** und die `Expression` Spalten.</span><span class="sxs-lookup"><span data-stu-id="d2a20-139">Select the variable in the list, and then update values in the `Name`, **Data Type**, `Value`, `Namespace`, **Raise Change Event**, **Description,** and `Expression` columns.</span></span>  
  
6.  <span data-ttu-id="d2a20-140">Wählen Sie die Variable in der Liste aus, und klicken Sie dann auf **Variable verschieben** , um den Bereich zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d2a20-140">Select the variable in the list, and then click **Move Variable** to change the scope.</span></span>  
  
7.  <span data-ttu-id="d2a20-141">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern**, um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d2a20-141">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="using-the-properties-window-to-set-properties"></a><span data-ttu-id="d2a20-142">Verwenden des Eigenschaftenfensters zum Festlegen von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d2a20-142">Using the Properties Window to Set Properties</span></span>  
  
#### <a name="to-set-the-properties-of-a-variable-by-using-the-properties-window"></a><span data-ttu-id="d2a20-143">So legen Sie die Eigenschaften einer Variablen mithilfe des Eigenschaftenfensters fest</span><span class="sxs-lookup"><span data-stu-id="d2a20-143">To set the properties of a variable by using the Properties window</span></span>  
  
1.  <span data-ttu-id="d2a20-144">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="d2a20-144">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="d2a20-145">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d2a20-145">In Solution Explorer, right-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="d2a20-146">Klicken Sie im Menü **Ansicht** auf **Eigenschaftenfenster**.</span><span class="sxs-lookup"><span data-stu-id="d2a20-146">On the **View** menu, click **Properties Window**.</span></span>  
  
4.  <span data-ttu-id="d2a20-147">Klicken Sie in [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer auf die Registerkarte **Paket-Explorer** , und erweitern Sie den Paketknoten.</span><span class="sxs-lookup"><span data-stu-id="d2a20-147">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Package Explorer** tab and expand the Package node.</span></span>  
  
5.  <span data-ttu-id="d2a20-148">Um Variablen mit Paketbereich zu ändern, erweitern Sie den Variablenknoten. Erweitern Sie anderenfalls den Ereignishandlerknoten oder den Knoten für Ausführbare Dateien, bis Sie den Variablenknoten finden, der die zu ändernde Variable enthält.</span><span class="sxs-lookup"><span data-stu-id="d2a20-148">To modify variables with package scope, expand the Variables node; otherwise, expand the Event Handlers or Executables nodes until you locate the Variables node that contains the variable that you want to modify.</span></span>  
  
6.  <span data-ttu-id="d2a20-149">Klicken Sie auf die Variable, deren Eigenschaften Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="d2a20-149">Click the variable whose properties you want to modify.</span></span>  
  
7.  <span data-ttu-id="d2a20-150">Aktualisieren Sie im Fenster **Eigenschaften** die Variableneigenschaften für den Lese-/Schreibzugriff.</span><span class="sxs-lookup"><span data-stu-id="d2a20-150">In the **Properties** window, update the read/write variable properties.</span></span> <span data-ttu-id="d2a20-151">Einige Eigenschaften sind für benutzerdefinierte Variablen auf Nur Lesen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d2a20-151">Some properties are read/read only for user-defined variables.</span></span>  
  
     <span data-ttu-id="d2a20-152">Weitere Informationen zu den Eigenschaften finden Sie unter [Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="d2a20-152">For more information about the properties, see [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md).</span></span>  
  
8.  <span data-ttu-id="d2a20-153">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern**, um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d2a20-153">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2a20-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d2a20-154">See Also</span></span>  
 <span data-ttu-id="d2a20-155">[Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="d2a20-155">[Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="d2a20-156">[Verwenden von Variablen in Paketen](../../2014/integration-services/use-variables-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="d2a20-156">[Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md) </span></span>  
 [<span data-ttu-id="d2a20-157">Hinzufügen, Löschen, Ändern des Bereichs von benutzerdefinierten Variablen in einem Paket</span><span class="sxs-lookup"><span data-stu-id="d2a20-157">Add, Delete, Change Scope of User-Defined Variable in a Package</span></span>](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md)  
  
  
