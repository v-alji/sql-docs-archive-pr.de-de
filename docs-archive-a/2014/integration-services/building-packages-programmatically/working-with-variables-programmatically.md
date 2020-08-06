---
title: Programmgesteuertes Arbeiten mit Variablen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- System namespace
- scope [Integration Services]
- variables [Integration Services], programmatically
- configuration files [Integration Services]
- Variables collection
- User namespace
- custom variables [Integration Services]
- variables [Integration Services], customizing
ms.assetid: c4b76a3d-94ca-4a8e-bb45-cb8bd0ea3ec1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2c903ee6adb8989eaeb93efbe943eca93c73eae4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723017"
---
# <a name="working-with-variables-programmatically"></a><span data-ttu-id="62e25-102">Programmgesteuertes Arbeiten mit Variablen</span><span class="sxs-lookup"><span data-stu-id="62e25-102">Working with Variables Programmatically</span></span>
  <span data-ttu-id="62e25-103">Variablen bieten die Möglichkeit, Werte dynamisch festzulegen und Prozesse in Paketen, Containern, Tasks und Ereignishandlern zu steuern.</span><span class="sxs-lookup"><span data-stu-id="62e25-103">Variables are a way to dynamically set values and control processes in packages, containers, tasks, and event handlers.</span></span> <span data-ttu-id="62e25-104">Variablen können auch von Rangfolgeneinschränkungen verwendet werden, um die Richtung des Datenflusses an andere Tasks zu steuern.</span><span class="sxs-lookup"><span data-stu-id="62e25-104">Variables can also be used by precedence constraints to control the direction of the flow of data to different tasks.</span></span> <span data-ttu-id="62e25-105">Variablen haben vielerlei Verwendungszwecke:</span><span class="sxs-lookup"><span data-stu-id="62e25-105">Variables have a variety of uses:</span></span>

-   <span data-ttu-id="62e25-106">Aktualisieren der Eigenschaften eines Pakets zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="62e25-106">Update properties of a package at run time.</span></span>

-   <span data-ttu-id="62e25-107">Auffüllen von Parameterwerten für Transact-SQL-Anweisungen zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="62e25-107">Populate parameter values for Transact-SQL statements at run time.</span></span>

-   <span data-ttu-id="62e25-108">Kontrollieren des Flusses einer Foreach-Schleife.</span><span class="sxs-lookup"><span data-stu-id="62e25-108">Control the flow of a Foreach loop.</span></span> <span data-ttu-id="62e25-109">Weitere Informationen finden Sie unter [Hinzufügen einer Enumeration zu einer Ablaufsteuerung](../control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="62e25-109">For more information, see [Add Enumeration to a Control Flow](../control-flow/control-flow.md).</span></span>

-   <span data-ttu-id="62e25-110">Steuern einer Rangfolgeneinschränkung durch ihre Verwendung in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="62e25-110">Control a precedence constraint by its use in an expression.</span></span> <span data-ttu-id="62e25-111">Eine Rangfolgeneinschränkung kann Variablen in die Einschränkungsdefinition einschließen.</span><span class="sxs-lookup"><span data-stu-id="62e25-111">A precedence constraint can include variables in the constraint definition.</span></span> <span data-ttu-id="62e25-112">Weitere Informationen finden Sie unter [Hinzufügen von Ausdrücken zu Rangfolgeneinschränkungen](../control-flow/precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="62e25-112">For more information, see [Add Expressions to Precedence Constraints](../control-flow/precedence-constraints.md).</span></span>

-   <span data-ttu-id="62e25-113">Kontrollieren der bedingten Wiederholung eines For-Schleifencontainers.</span><span class="sxs-lookup"><span data-stu-id="62e25-113">Control the conditional repeat of a For Loop container.</span></span> <span data-ttu-id="62e25-114">Weitere Informationen finden Sie unter [Hinzufügen einer Iteration zu einer Ablaufsteuerung](../add-iteration-to-a-control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="62e25-114">For more information, see [Add Iteration to a Control Flow](../add-iteration-to-a-control-flow.md).</span></span>

-   <span data-ttu-id="62e25-115">Erstellen von Ausdrücken, die Variablenwerte einschließen.</span><span class="sxs-lookup"><span data-stu-id="62e25-115">Build expressions that include variable values.</span></span>

-   <span data-ttu-id="62e25-116">Sie können benutzerdefinierte Variablen für alle Containertypen erstellen: Pakete, **Foreach-Schleifencontainer**, **For-Schleifencontainer**, **Sequenzcontainer**, TasksHosts und Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="62e25-116">You can create custom variables for all container types: packages, **Foreach Loop** containers, **For Loop** containers, **Sequence** containers, TaskHosts, and event handlers.</span></span> <span data-ttu-id="62e25-117">Weitere Informationen finden Sie unter [Integration Services-Variablen &#40;SSIS&#41;](../integration-services-ssis-variables.md) und [Verwenden von Variablen in Paketen](../use-variables-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="62e25-117">For more information, see [Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) and [Use Variables in Packages](../use-variables-in-packages.md).</span></span>

## <a name="scope"></a><span data-ttu-id="62e25-118">`Scope`</span><span class="sxs-lookup"><span data-stu-id="62e25-118">Scope</span></span>
 <span data-ttu-id="62e25-119">Jeder Container weist seine eigene <xref:Microsoft.SqlServer.Dts.Runtime.Variables>-Auflistung auf.</span><span class="sxs-lookup"><span data-stu-id="62e25-119">Each container has its own <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection.</span></span> <span data-ttu-id="62e25-120">Wenn eine neue Variable erstellt wird, liegt diese innerhalb des Bereichs seines übergeordneten Containers.</span><span class="sxs-lookup"><span data-stu-id="62e25-120">When a new variable is created, it is within the scope of its parent container.</span></span> <span data-ttu-id="62e25-121">Da sich der Paketcontainer ganz oben in der Containerhierarchie befindet, funktionieren Variablen mit Paketbereich wie globale Variablen und sind für alle Container innerhalb des Pakets sichtbar.</span><span class="sxs-lookup"><span data-stu-id="62e25-121">Because the package container is at the top of the container hierarchy, variables with package scope function like global variables, and are visible to all containers within the package.</span></span> <span data-ttu-id="62e25-122">Auf die Auflistung von Variablen für den Container kann über die <xref:Microsoft.SqlServer.Dts.Runtime.Variables>-Auflistung auch von untergeordneten Elementen des Containers zugegriffen werden, indem entweder der Variablenname oder der Index der Variablen in der Auflistung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="62e25-122">The collection of variables for the container can also be accessed by the children of the container through the <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection, by using either the variable name or the variable's index in the collection.</span></span>

 <span data-ttu-id="62e25-123">Da die Sichtbarkeit einer Variablen von oben nach unten verläuft, sind Variablen, die auf der Paketebene deklariert werden, für alle Container in dem Paket sichtbar.</span><span class="sxs-lookup"><span data-stu-id="62e25-123">Because the visibility of a variable is scoped from the top down, variables declared at the package level are visible to all the containers in the package.</span></span> <span data-ttu-id="62e25-124">Die <xref:Microsoft.SqlServer.Dts.Runtime.Variables>-Auflistung in einem Container umfasst daher alle Variablen, die neben den eigenen Variablen des Containers auch zu seinem übergeordneten Element gehören.</span><span class="sxs-lookup"><span data-stu-id="62e25-124">Therefore, the <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection on a container includes all the variables that belong to its parent in addition to its own variables</span></span>

 <span data-ttu-id="62e25-125">Die Variablen, die in einem Task enthalten sind, sind dagegen hinsichtlich Bereich und Sichtbarkeit eingeschränkt und nur für den Task sichtbar.</span><span class="sxs-lookup"><span data-stu-id="62e25-125">Conversely, the variables that are contained in a task are limited in scope and visibility, and are only visible to the task.</span></span>

 <span data-ttu-id="62e25-126">Wenn ein Paket andere Pakete ausführt, sind die in dem Bereich des aufrufenden Pakets definierten Variablen für das aufgerufene Paket verfügbar.</span><span class="sxs-lookup"><span data-stu-id="62e25-126">If a package runs other packages, the variables defined in the scope of the calling package are available to the called package.</span></span> <span data-ttu-id="62e25-127">Die einzige Ausnahme tritt auf, wenn eine gleichnamige Variable im aufgerufenen Paket vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="62e25-127">The only exception occurs when a same-named variable exists in the called package.</span></span> <span data-ttu-id="62e25-128">Bei diesem Konflikt wird der Wert des aufrufenden Pakets von dem Variablenwert des aufgerufenen Pakets überschrieben.</span><span class="sxs-lookup"><span data-stu-id="62e25-128">When this collision occurs, the variable value in the called package overrides the value from the calling package.</span></span> <span data-ttu-id="62e25-129">Die in dem Bereich des aufgerufenen Pakets definierten Variablen sind niemals für das aufrufende Paket verfügbar.</span><span class="sxs-lookup"><span data-stu-id="62e25-129">Variables defined in the scope of the called package are never available back to the calling package.</span></span>

 <span data-ttu-id="62e25-130">Im folgenden Beispielcode wird eine Variable `myCustomVar` programmgesteuert in dem Paketbereich erstellt. Diese führt dann eine Iteration durch alle Variablen durch, die für das Paket sichtbar sind. Dabei wird der Name, der Datentyp und der Wert ausgedruckt.</span><span class="sxs-lookup"><span data-stu-id="62e25-130">The following code example programmatically creates a variable, `myCustomVar`, at the package scope, and then iterates through all the variables visible to the package, printing their name, data type, and value.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.SqlServer.Dts.Samples
{
  class Program
  {
    static void Main(string[] args)
    {
      Application app = new Application();
      // Load a sample package that contains a variable that sets the file name.
      Package pkg = app.LoadPackage(
        @"C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" +
        @"\Package Samples\CaptureDataLineage Sample\CaptureDataLineage\CaptureDataLineage.dtsx",
        null);
      Variables pkgVars = pkg.Variables;
      Variable myVar = pkg.Variables.Add("myCustomVar", false, "User", "3");
      foreach (Variable pkgVar in pkgVars)
      {
        Console.WriteLine("Variable: {0}, {1}, {2}", pkgVar.Name,
          pkgVar.DataType, pkgVar.Value.ToString());
      }
      Console.Read();
    }
  }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime

Module Module1

  Sub Main()

    Dim app As Application = New Application()
    ' Load a sample package that contains a variable that sets the file name.
    Dim pkg As Package = app.LoadPackage( _
      "C:\Program Files\Microsoft SQL Server\100\Samples\Integration Services" & _
      "\Package Samples\CaptureDataLineage Sample\CaptureDataLineage\CaptureDataLineage.dtsx", _
      Nothing)
    Dim pkgVars As Variables = pkg.Variables
    Dim myVar As Variable = pkg.Variables.Add("myCustomVar", False, "User", "3")
    Dim pkgVar As Variable
    For Each pkgVar In pkgVars
      Console.WriteLine("Variable: {0}, {1}, {2}", pkgVar.Name, _
        pkgVar.DataType, pkgVar.Value.ToString())
    Next
    Console.Read()

  End Sub

End Module
```

 <span data-ttu-id="62e25-131">**Beispielausgabe:**</span><span class="sxs-lookup"><span data-stu-id="62e25-131">**Sample Output:**</span></span>

 `Variable: CancelEvent, Int32, 0`

 `Variable: CreationDate, DateTime, 4/18/2003 11:57:00 AM`

 `Variable: CreatorComputerName, String,`

 `Variable: CreatorName, String,`

 `Variable: ExecutionInstanceGUID, String, {237AB5A4-7E59-4FC9-8D61-E8F20363DF25}`

 `Variable: FileName, String, Junk`

 `Variable: InteractiveMode, Boolean, False`

 `Variable: LocaleID, Int32, 1033`

 `Variable: MachineName, String, MYCOMPUTERNAME`

 `Variable: myCustomVar, String, 3`

 `Variable: OfflineMode, Boolean, False`

 `Variable: PackageID, String, {F0D2E396-A6A5-42AE-9467-04CE946A810C}`

 `Variable: PackageName, String, DTSPackage1`

 `Variable: StartTime, DateTime, 1/28/2005 7:55:39 AM`

 `Variable: UserName, String, <domain>\<userid>`

 `Variable: VersionBuild, Int32, 198`

 `Variable: VersionComments, String,`

 `Variable: VersionGUID, String, {90E105B4-B4AF-4263-9CBD-C2050C2D6148}`

 `Variable: VersionMajor, Int32, 1`

 `Variable: VersionMinor, Int32, 0`

 <span data-ttu-id="62e25-132">Beachten Sie, dass alle im **System**-Namespace bewerteten Variablen dem Paket zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="62e25-132">Notice that all the variables scoped in the **System** namespace are available to the package.</span></span> <span data-ttu-id="62e25-133">Weitere Informationen finden Sie unter [System Variables](../system-variables.md).</span><span class="sxs-lookup"><span data-stu-id="62e25-133">For more information, see [System Variables](../system-variables.md).</span></span>

## <a name="namespaces"></a><span data-ttu-id="62e25-134">Namespaces</span><span class="sxs-lookup"><span data-stu-id="62e25-134">Namespaces</span></span>
 [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="62e25-135">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) stellt zwei Standardnamespaces für Variablen bereit: **User** und **System**.</span><span class="sxs-lookup"><span data-stu-id="62e25-135">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) provides two default namespaces where variables reside; **User** and **System** namespaces.</span></span> <span data-ttu-id="62e25-136">Standardmäßig werden dem **User**-Namespace alle vom Entwickler erstellten benutzerdefinierten Variablen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="62e25-136">By default, any custom variable created by the developer is added to the **User** namespace.</span></span> <span data-ttu-id="62e25-137">Systemvariablen befinden sich im **System**-Namespace.</span><span class="sxs-lookup"><span data-stu-id="62e25-137">System variables reside in the **System** namespace.</span></span> <span data-ttu-id="62e25-138">Sie können neben dem **User**-Namespace zusätzliche Namespaces für benutzerdefinierte Variablen erstellen und den Namen des **User**-Namespaces ändern. Es ist jedoch nicht möglich, Variablen im **System**-Namespace hinzuzufügen oder zu ändern oder Systemvariablen einem anderen Namespace zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="62e25-138">You can create additional namespaces other than the **User** namespace to hold custom variables, and you can change the name of the **User** namespace, but you cannot add or modify variables in the **System** namespace, or assign system variables to a different namespace.</span></span>

 <span data-ttu-id="62e25-139">Die verfügbaren Systemvariablen sind je nach Containertyp unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="62e25-139">The system variables that are available differ depending on the container type.</span></span> <span data-ttu-id="62e25-140">Eine Liste der für Pakete, Container, Tasks und Ereignishandler verfügbaren Systemvariablen finden Sie unter [System Variables](../system-variables.md) (Systemvariablen).</span><span class="sxs-lookup"><span data-stu-id="62e25-140">For a list of the system variables available to packages, containers, tasks, and event handlers, see [System Variables](../system-variables.md).</span></span>

## <a name="value"></a><span data-ttu-id="62e25-141">value</span><span class="sxs-lookup"><span data-stu-id="62e25-141">Value</span></span>
 <span data-ttu-id="62e25-142">Der Wert einer benutzerdefinierten Variablen kann ein Literal oder ein Ausdruck sein:</span><span class="sxs-lookup"><span data-stu-id="62e25-142">The value of a custom variable can be a literal or an expression:</span></span>

-   <span data-ttu-id="62e25-143">Wenn die Variable einen Literalwert enthalten soll, legen Sie den Wert seiner <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="62e25-143">If you want the variable to contain a literal value, set the value of its <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> property.</span></span>

-   <span data-ttu-id="62e25-144">Wenn die Variable einen Ausdruck enthalten soll, sodass Sie die Ergebnisse des Ausdrucks als Wert verwenden können, legen Sie die <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A>-Eigenschaft der Variablen auf `true` fest, und geben Sie einen Ausdruck in der <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Expression%2A>-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="62e25-144">If you want the variable to contain an expression, so that you can use the results of the expression as its value, set the <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> property of the variable to `true`, and provide an expression in the <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Expression%2A> property.</span></span> <span data-ttu-id="62e25-145">Zur Laufzeit wird der Ausdruck ausgewertet, und das Ergebnis des Ausdrucks wird als Wert der Variablen verwendet.</span><span class="sxs-lookup"><span data-stu-id="62e25-145">At run time, the expression is evaluated, and the result of the expression is used as the value of the variable.</span></span> <span data-ttu-id="62e25-146">Wenn z. B. die Ausdruckseigenschaft einer Variablen`"100 * 2""100 * 2"` ist, wird die Variable auf einen Wert von 200 ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="62e25-146">For example, if the expression property of a variable is `"100 * 2""100 * 2"`, the variable evaluates to a value of 200.</span></span>

 <span data-ttu-id="62e25-147">Für eine Variable kann der Wert ihres <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A> nicht explizit festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="62e25-147">For a variable, you cannot explicitly set the value of its <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A>.</span></span> <span data-ttu-id="62e25-148">Der Wert <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A> wird aus dem Startwert, der der Variablen zugewiesen ist, abgeleitet und kann nachträglich nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="62e25-148">The <xref:Microsoft.SqlServer.Dts.Runtime.Variable.DataType%2A> value is inferred from the initial value assigned to the variable, and cannot be changed afterward.</span></span> <span data-ttu-id="62e25-149">Weitere Informationen zu Variablendatentypen finden Sie unter [Integration Services Data Types](../data-flow/integration-services-data-types.md) (Integration Services-Datentypen).</span><span class="sxs-lookup"><span data-stu-id="62e25-149">For more information about variable data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

 <span data-ttu-id="62e25-150">Im folgenden Codebeispiel wird eine neue Variable erstellt, <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> auf `true` festgelegt, der Ausdruck `"100 * 2"` der Ausdruckseigenschaft der Variablen zugewiesen und dann der Wert der Variablen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="62e25-150">The following code example creates a new variable, sets <xref:Microsoft.SqlServer.Dts.Runtime.Variable.EvaluateAsExpression%2A> to `true`, assigns the expression `"100 * 2"` to the expression property of the variable, and then outputs the value of the variable.</span></span>

```csharp
using System;
using Microsoft.SqlServer.Dts.Runtime;

namespace Microsoft.SqlServer.Dts.Samples
{
  class Program
  {
    static void Main(string[] args)
    {
      Package pkg = new Package();
      Variable v100 = pkg.Variables.Add("myVar", false, "", 1);
      v100.EvaluateAsExpression = true;
      v100.Expression = "100 * 2";
      Console.WriteLine("Expression for myVar: {0}", 
        v100.Properties["Expression"].GetValue(v100));
      Console.WriteLine("Value of myVar: {0}", v100.Value.ToString());
      Console.Read();
    }
  }
}
```

```vb
Imports Microsoft.SqlServer.Dts.Runtime

Module Module1

  Sub Main()

    Dim pkg As Package = New Package
    Dim v100 As Variable = pkg.Variables.Add("myVar", False, "", 1)
    v100.EvaluateAsExpression = True
    v100.Expression = "100 * 2"
    Console.WriteLine("Expression for myVar: {0}", _
      v100.Properties("Expression").GetValue(v100))
    Console.WriteLine("Value of myVar: {0}", v100.Value.ToString)
    Console.Read()

  End Sub

End Module
```

 <span data-ttu-id="62e25-151">**Beispielausgabe:**</span><span class="sxs-lookup"><span data-stu-id="62e25-151">**Sample Output:**</span></span>

 `Expression for myVar: 100 * 2`

 `Value of myVar: 200`

 <span data-ttu-id="62e25-152">Der Ausdruck muss ein gültiger Ausdruck sein, der die [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Ausdruckssyntax verwendet.</span><span class="sxs-lookup"><span data-stu-id="62e25-152">The expression must be a valid expression that uses the [!INCLUDE[ssIS](../../includes/ssis-md.md)] expression syntax.</span></span> <span data-ttu-id="62e25-153">Neben den Operatoren und Funktionen, die der Ausdruck bereitstellt, sind Literale in Variablenausdrücke zulässig, Ausdrücke können jedoch nicht auf andere Variablen oder Spalten verweisen.</span><span class="sxs-lookup"><span data-stu-id="62e25-153">Literals are permitted in variable expressions, in addition to the operators and functions that the expression syntax provides, but expressions cannot reference other variables or columns.</span></span> <span data-ttu-id="62e25-154">Weitere Informationen finden Sie unter [Integration Services-Ausdrücke &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md)ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="62e25-154">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md).</span></span>

## <a name="configuration-files"></a><span data-ttu-id="62e25-155">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="62e25-155">Configuration Files</span></span>
 <span data-ttu-id="62e25-156">Wenn eine Konfigurationsdatei eine benutzerdefinierte Variable einschließt, kann die Variable zur Laufzeit aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="62e25-156">If a configuration file includes a custom variable, the variable can be updated at run time.</span></span> <span data-ttu-id="62e25-157">Dies bedeutet, dass der Wert der ursprünglich in dem Paket enthaltenen Variablen beim Ausführen des Pakets durch einen neuen Wert aus der Konfigurationsdatei ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="62e25-157">What this means is that when the package runs, the value of the variable originally in the package is replaced with a new value from the configuration file.</span></span> <span data-ttu-id="62e25-158">Diese Ersetzungstechnik ist hilfreich, wenn ein Paket für mehrere Server bereitgestellt wird, die unterschiedliche Variablenwerte erfordern.</span><span class="sxs-lookup"><span data-stu-id="62e25-158">This replacement technique is useful when a package is deployed to multiple servers that require different variable values.</span></span> <span data-ttu-id="62e25-159">In einer Variablen kann beispielsweise angegeben werden, wie oft ein **Foreach-Schleifencontainer** seinen Workflow wiederholt, oder es können die Empfänger aufgelistet werden, an die von einem Ereignishandler eine E-Mail gesendet wird, wenn ein Fehler ausgelöst wird. In einer Variablen kann auch die Anzahl von Fehlern geändert werden, die auftreten können, bevor für das Paket ein Fehler gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="62e25-159">For example, a variable can specify the number of times a **Foreach Loop** container repeats its workflow, or list the recipients that an event handler sends e-mail to when an error is raised, or change the number of errors that can occur before the package fails.</span></span> <span data-ttu-id="62e25-160">Diese Variablen werden dynamisch in Konfigurationsdateien für jede Umgebung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="62e25-160">These variables are dynamically provided in configuration files for each environment.</span></span> <span data-ttu-id="62e25-161">Daher sind nur Lese-/Schreibvariablen in Konfigurationsdateien zulässig.</span><span class="sxs-lookup"><span data-stu-id="62e25-161">Therefore, only variables that are read/write are allowed in configuration files.</span></span> <span data-ttu-id="62e25-162">Weitere Informationen finden Sie unter [Erstellen von Paketkonfigurationen](../create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="62e25-162">For more information, see [Create Package Configurations](../create-package-configurations.md).</span></span>

<span data-ttu-id="62e25-163">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="62e25-163">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="62e25-164">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="62e25-164">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="62e25-165">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="62e25-165">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="62e25-166">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="62e25-166">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="62e25-167">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="62e25-167">See Also</span></span>
 <span data-ttu-id="62e25-168">[Integration Services &#40;SSIS-&#41; Variablen](../integration-services-ssis-variables.md) Variablen [in Paketen verwenden](../use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="62e25-168">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) [Use Variables in Packages](../use-variables-in-packages.md)</span></span>


