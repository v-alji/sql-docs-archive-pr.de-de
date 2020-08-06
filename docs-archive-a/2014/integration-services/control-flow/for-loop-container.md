---
title: For-Schleifencontainer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.forloopcontainerdetails.f1
helpviewer_keywords:
- repeating control flow
- containers [Integration Services], For Loop
- For Loop containers
ms.assetid: 44cf7355-992b-4bbf-a28c-bfb012de06f6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a6c864779237fdbf4dd249f87b7c06655293c047
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607947"
---
# <a name="for-loop-container"></a><span data-ttu-id="10b77-102">For-Schleifencontainer</span><span class="sxs-lookup"><span data-stu-id="10b77-102">For Loop Container</span></span>
  <span data-ttu-id="10b77-103">Der For-Schleifencontainer definiert die Wiederholung einer Ablaufsteuerung in einem Paket.</span><span class="sxs-lookup"><span data-stu-id="10b77-103">The For Loop container defines a repeating control flow in a package.</span></span> <span data-ttu-id="10b77-104">Die Schleifenimplementierung ist mit der **For** -Schleifenstruktur in Programmiersprachen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="10b77-104">The loop implementation is similar to the **For** looping structure in programming languages.</span></span> <span data-ttu-id="10b77-105">Bei jeder Wiederholung der Schleife wertet der For-Schleifencontainer einen Ausdruck aus und wiederholt dessen Workflow, bis der Ausdruck zu `False` ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="10b77-105">In each repeat of the loop, the For Loop container evaluates an expression and repeats its workflow until the expression evaluates to `False`.</span></span>  
  
 <span data-ttu-id="10b77-106">Der For-Schleifencontainer verwendet die folgenden Elemente zum Definieren der Schleife:</span><span class="sxs-lookup"><span data-stu-id="10b77-106">The For Loop container usesthe following elements to define the loop:</span></span>  
  
-   <span data-ttu-id="10b77-107">Einen optionalen Initialisierungsausdruck, der den Schleifenzählern Werte zuweist.</span><span class="sxs-lookup"><span data-stu-id="10b77-107">An optional initialization expression that assigns values to the loop counters.</span></span>  
  
-   <span data-ttu-id="10b77-108">Einen Auswertungsausdruck, der den Ausdruck enthält, um zu testen, ob die Schleife beendet oder fortgesetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="10b77-108">An evaluation expression that contains the expression used to test whether the loop should stop or continue.</span></span>  
  
-   <span data-ttu-id="10b77-109">Einen optionalen Iterationsausdruck, der den Schleifenzähler inkrementiert oder reduziert.</span><span class="sxs-lookup"><span data-stu-id="10b77-109">An optional iteration expression that increments or decrements the loop counter.</span></span>  
  
 <span data-ttu-id="10b77-110">Das folgende Diagramm zeigt einen For-Schleifencontainer mit einem Task Mail senden.</span><span class="sxs-lookup"><span data-stu-id="10b77-110">The following diagram shows a For Loop container with a Send Mail task.</span></span> <span data-ttu-id="10b77-111">Falls der Initialisierungsausdruck `@Counter = 0`ist, lautet der Auswertungsausdruck `@Counter < 4`. Falls der Iterationsausdruck `@Counter = @Counter + 1`ist, wird die Schleife viermal wiederholt, und es werden vier E-Mail-Nachrichten gesendet.</span><span class="sxs-lookup"><span data-stu-id="10b77-111">If the initialization expression is `@Counter = 0`, the evaluation expression is `@Counter < 4`, and the iteration expression is `@Counter = @Counter + 1`, the loop repeats four times and sends four e-mail messages.</span></span>  
  
 <span data-ttu-id="10b77-112">![For-Schleifencontainer wiederholt einen Task viermal](../media/ssis-forloop.gif "For-Schleifencontainer wiederholt einen Task viermal")</span><span class="sxs-lookup"><span data-stu-id="10b77-112">![A For Loop container repeats a task four times](../media/ssis-forloop.gif "A For Loop container repeats a task four times")</span></span>  
  
 <span data-ttu-id="10b77-113">Die Ausdrücke müssen für gültige [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Ausdrücke sein.</span><span class="sxs-lookup"><span data-stu-id="10b77-113">The expressions must be valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expressions.</span></span>  
  
 <span data-ttu-id="10b77-114">Zum Erstellen der Initialisierungs- und Zuweisungsausdrücke können Sie den Zuweisungsoperator (=) verwenden.</span><span class="sxs-lookup"><span data-stu-id="10b77-114">To create the initialization and assignment expressions, you can use the assignment operator (=).</span></span> <span data-ttu-id="10b77-115">Dieser Operator wird ansonsten nicht von der SQL Server Integration Services-Ausdrucksgrammatik unterstützt und kann nur von Initialisierungs- und Zuweisungsausdrücken im For-Schleifencontainer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="10b77-115">This operator is not otherwise supported by the Integration Services expression grammar and can only be used by the initialization and assignment expression types in the For Loop container.</span></span> <span data-ttu-id="10b77-116">Jeder Ausdruck, der den Zuweisungsoperator verwendet, erfordert die Syntax `@Var = <expression>`. Hierbei ist **Var** eine Laufzeitvariable, und \<expression> ist ein Ausdruck, der den Regeln der [!INCLUDE[ssIS](../../../includes/ssis-md.md)]-Ausdruckssyntax entspricht.</span><span class="sxs-lookup"><span data-stu-id="10b77-116">Any expression that uses the assignment operator must have the syntax `@Var = <expression>`, where **Var** is a run-time variable and \<expression> is an expression that follows the rules of the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] expression syntax.</span></span> <span data-ttu-id="10b77-117">Für diesen Ausdruck sind die Variablen, Literale sowie Operatoren und Funktionen zulässig, die von der SSIS-Ausdrucksgrammatik unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="10b77-117">The expression can include the variables, literals, and any operators and functions that the SSIS expression grammar supports.</span></span> <span data-ttu-id="10b77-118">Der Ausdruck muss zu einem Datentyp ausgewertet werden, der in den Datentyp der Variablen umgewandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="10b77-118">The expression must evaluate to a data type that can be cast to the data type of the variable.</span></span>  
  
 <span data-ttu-id="10b77-119">Für einen For-Schleifencontainer ist nur ein Auswertungsausdruck zulässig.</span><span class="sxs-lookup"><span data-stu-id="10b77-119">A For Loop container can have only one evaluation expression.</span></span> <span data-ttu-id="10b77-120">Dies bedeutet, dass der For-Schleifencontainer alle Ablaufsteuerungselemente mit der gleichen Häufigkeit ausführt.</span><span class="sxs-lookup"><span data-stu-id="10b77-120">This means that the For Loop container runs all its control flow elements the same number of times.</span></span> <span data-ttu-id="10b77-121">Der For-Schleifencontainer kann andere For-Schleifencontainer enthalten, sodass Sie geschachtelte Schleifen erstellen und komplexe Schleifen in Pakete implementieren können.</span><span class="sxs-lookup"><span data-stu-id="10b77-121">Because the For Loop container can include other For Loop containers, you can build nested loops and implement complex looping in packages.</span></span>  
  
 <span data-ttu-id="10b77-122">Sie können eine Transaktionseigenschaft für den For-Schleifencontainer festlegen, um eine Transaktion für eine Teilmenge der Paketablaufsteuerung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="10b77-122">You can set a transaction property on the For Loop container to define a transaction for a subset of the package control flow.</span></span> <span data-ttu-id="10b77-123">Auf diese Weise können Sie Transaktionen mit feinerer Granularität verwalten.</span><span class="sxs-lookup"><span data-stu-id="10b77-123">In this way, you can manage transactions at a more granular level.</span></span> <span data-ttu-id="10b77-124">Angenommen, ein For-Schleifencontainer wiederholt eine Ablaufsteuerung, die Daten in einer Tabelle mehrmals aktualisiert. In diesem Fall können Sie für die For-Schleife und deren Ablaufsteuerung die Verwendung einer Transaktion konfigurieren, um sicherzustellen, dass entweder alle oder überhaupt keine Daten aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="10b77-124">For example, if a For Loop container repeats a control flow that updates data in a table multiple times, you can configure the For Loop and its control flow to use a transaction to ensure that if not all data is updated successfully, no data is updated.</span></span> <span data-ttu-id="10b77-125">Weitere Informationen finden Sie unter [Integration Services-Transaktionen](../integration-services-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="10b77-125">For more information, see [Integration Services Transactions](../integration-services-transactions.md).</span></span>  
  
## <a name="configuration-of-the-for-loop-container"></a><span data-ttu-id="10b77-126">Konfiguration des For-Schleifencontainers</span><span class="sxs-lookup"><span data-stu-id="10b77-126">Configuration of the For Loop Container</span></span>  
 <span data-ttu-id="10b77-127">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="10b77-127">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="10b77-128">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="10b77-128">For more information about the properties that you can set in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="10b77-129">For-Schleifen-Editor</span><span class="sxs-lookup"><span data-stu-id="10b77-129">For Loop Editor</span></span>](../for-loop-editor.md)  
  
-   [<span data-ttu-id="10b77-130">Seite Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="10b77-130">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="10b77-131">Weitere Informationen zum programmgesteuerten Festlegen dieser Eigenschaften finden Sie in der Dokumentation zur **T:Microsoft.SqlServer.Dts.Runtime.ForLoop** -Klasse im Entwicklerhandbuch.</span><span class="sxs-lookup"><span data-stu-id="10b77-131">For more information about programmatically setting these properties, see documentation for the **T:Microsoft.SqlServer.Dts.Runtime.ForLoop** class in the Developer Guide.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="10b77-132">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="10b77-132">Related Tasks</span></span>  
 <span data-ttu-id="10b77-133">Informationen zum Konfigurieren eines For-Schleifencontainers finden Sie in den nachfolgenden Themen.</span><span class="sxs-lookup"><span data-stu-id="10b77-133">For information about how to configure a For Loop Container, see the following topics.</span></span>  
  
-   [<span data-ttu-id="10b77-134">Konfigurieren eines For-Schleifencontainers</span><span class="sxs-lookup"><span data-stu-id="10b77-134">Configure a For Loop Container</span></span>](for-loop-container.md)  
  
-   [<span data-ttu-id="10b77-135">Festlegen der Eigenschaften eines Tasks oder Containers</span><span class="sxs-lookup"><span data-stu-id="10b77-135">Set the Properties of a Task or Container</span></span>](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a><span data-ttu-id="10b77-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10b77-136">See Also</span></span>  
 <span data-ttu-id="10b77-137">[Ablaufsteuerung](control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="10b77-137">[Control Flow](control-flow.md) </span></span>  
 [<span data-ttu-id="10b77-138">Integration Services-Ausdrücke &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="10b77-138">Integration Services &#40;SSIS&#41; Expressions</span></span>](../expressions/integration-services-ssis-expressions.md)  
  
  
