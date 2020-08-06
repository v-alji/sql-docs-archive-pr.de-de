---
title: Hinzufügen oder Ändern eines Eigenschaftsausdrucks | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- expressions [Integration Services], creating
- expressions [Integration Services], property expressions
ms.assetid: cb5da499-065f-4fa6-9f6d-5bc5f385241e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d6d12fbe46930818af2b47b59620963d39616e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619977"
---
# <a name="add-or-change-a-property-expression"></a><span data-ttu-id="f2f3c-102">Hinzufügen oder Ändern eines Eigenschaftsausdrucks</span><span class="sxs-lookup"><span data-stu-id="f2f3c-102">Add or Change a Property Expression</span></span>
  <span data-ttu-id="f2f3c-103">Sie können Eigenschaftsausdrücke für Pakete, Tasks, Foreach-Schleifencontainer, For-Schleifencontainer, Sequenzcontainer, Ereignishandler, Verbindungs-Manager auf Paket- und Projektebene sowie für Protokollanbieter erstellen.</span><span class="sxs-lookup"><span data-stu-id="f2f3c-103">You can create property expressions for packages, tasks, Foreach Loop containers, For Loop containers, Sequence containers, event handlers, package and project level connection managers, and log providers.</span></span>  
  
 <span data-ttu-id="f2f3c-104">Um Eigenschaftsausdrücke zu erstellen oder zu ändern, können Sie entweder den **Eigenschaftsausdrucks-Editor** oder den **Ausdrucks-Generator**verwenden.</span><span class="sxs-lookup"><span data-stu-id="f2f3c-104">To create or change property expressions, you can use either the **Property Expressions Editor** or **Expression Builder**.</span></span> <span data-ttu-id="f2f3c-105">Der **Eigenschaftsausdrucks-Editor** kann entweder über die benutzerdefinierten Editoren, die für Tasks und Container verfügbar sind, oder über das Fenster **Eigenschaften** aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f2f3c-105">The **Property Expressions Editor** can be accessed from either the custom editors that are available for tasks and containers, or from the **Properties** window.</span></span> <span data-ttu-id="f2f3c-106">Auf den**Ausdrucks-Generator** kann über den **Eigenschaftsausdrucks-Editor**zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="f2f3c-106">**Expression Builder** can be accessed from inside the **Property Expressions Editor**.</span></span> <span data-ttu-id="f2f3c-107">Sie können zwar sowohl im **Eigenschaftsausdrucks-Editor** als auch im **Ausdrucks-Generator**Ausdrücke schreiben, der **Ausdrucks-Generator** bietet jedoch außerdem eine Reihe grafischer Tools, mit denen komplexe Ausdrücke problemlos erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="f2f3c-107">While you can write expressions in either the **Property Expressions Editor** or **Expression Builder**, **Expression Builder** provides a graphical set of tools that makes it simple to build complex expressions.</span></span>  
  
 <span data-ttu-id="f2f3c-108">Weitere Informationen zu Syntax, Operatoren und Funktionen, die [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] bereitstellt, finden Sie unter [Operatoren &#40;SSIS-Ausdruck&#41;](operators-ssis-expression.md) und [Funktionen &#40;SSIS-Ausdruck&#41;](functions-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="f2f3c-108">To learn more about the syntax, operators, and functions that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides, see [Operators &#40;SSIS Expression&#41;](operators-ssis-expression.md) and [Functions &#40;SSIS Expression&#41;](functions-ssis-expression.md).</span></span> <span data-ttu-id="f2f3c-109">Das Thema für die einzelnen Operatoren oder Funktionen schließen Beispiele für das Verwenden des Operators bzw. der Funktion in einem Ausdruck ein.</span><span class="sxs-lookup"><span data-stu-id="f2f3c-109">The topic for each operator or function includes examples of using that operator or function in an expression.</span></span> <span data-ttu-id="f2f3c-110">Beispiele für komplexere Ausdrücke finden Sie unter [Verwenden von Eigenschaftsausdrücken in Paketen](use-property-expressions-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="f2f3c-110">For examples of more complex expressions, see [Use Property Expressions in Packages](use-property-expressions-in-packages.md).</span></span>  
  
### <a name="to-create-or-change-a-property-expression"></a><span data-ttu-id="f2f3c-111">So fügen Sie einen Eigenschaftsausdruck hinzu oder ändern ihn</span><span class="sxs-lookup"><span data-stu-id="f2f3c-111">To create or change a property expression</span></span>  
  
1.  <span data-ttu-id="f2f3c-112">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]das Projekt mit dem gewünschten [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Paket.</span><span class="sxs-lookup"><span data-stu-id="f2f3c-112">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project that contains the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package you want.</span></span>  
  
2.  <span data-ttu-id="f2f3c-113">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen, und führen Sie dann eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="f2f3c-113">In Solution Explorer, double-click the package to open it, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="f2f3c-114">Wenn es sich bei dem Element um einen Task oder einen Container handelt, doppelklicken Sie darauf, und klicken Sie dann im Editor auf **Ausdrücke** .</span><span class="sxs-lookup"><span data-stu-id="f2f3c-114">If the item is a task or a container, double-click the item, and then click **Expressions** in the editor.</span></span>  
  
    -   <span data-ttu-id="f2f3c-115">Klicken Sie mit der rechten Maustaste auf das Element, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f2f3c-115">Right-click the item and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="f2f3c-116">Klicken Sie in das Feld **Ausdrücke**, und klicken Sie dann auf die Auslassungspunkte (…).</span><span class="sxs-lookup"><span data-stu-id="f2f3c-116">Click in the **Expressions** box and then click the ellipsis (...).</span></span>  
  
4.  <span data-ttu-id="f2f3c-117">Wählen Sie im **Eigenschaftsausdrucks-Editor**eine Eigenschaft in der Liste **Eigenschaft** aus, und gehen Sie dann wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="f2f3c-117">In the **Property Expressions Editor**, select a property in the **Property** list, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="f2f3c-118">Geben Sie in die Spalte **Ausdruck** direkt einen Ausdruck ein oder ändern Sie ihn, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2f3c-118">Type or change the property expression directly in the **Expression** column, and then click **OK**.</span></span>  
  
         <span data-ttu-id="f2f3c-119">Oder</span><span class="sxs-lookup"><span data-stu-id="f2f3c-119">-or-</span></span>  
  
    -   <span data-ttu-id="f2f3c-120">Klicken Sie in der Ausdruckszeile der Eigenschaft auf die Auslassungspunkte (...), um den **Ausdrucks-Generator** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f2f3c-120">Click the ellipsis (...) in the expression row of the property to open the **Expression Builder**.</span></span>  
  
5.  <span data-ttu-id="f2f3c-121">(Optional) Führen Sie im **Ausdrucks-Generator**eine der folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="f2f3c-121">(Optional) In the **Expression Builder**, do any of the following tasks:</span></span>  
  
    -   <span data-ttu-id="f2f3c-122">Erweitern Sie die Option **Variablen**, um auf die System- und benutzerdefinierten Variablen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f2f3c-122">To access system and user-defined variables, expand **Variables**.</span></span>  
  
    -   <span data-ttu-id="f2f3c-123">Erweitern Sie die Option [!INCLUDE[ssIS](../../includes/ssis-md.md)] Mathematische Funktionen **,** Zeichenfolgenfunktionen **,** Datums-/Uhrzeitfunktionen **,** NULL-Funktionen **,** Typumwandlungen **und**Operatoren **, um auf die Funktionen, die Umwandlungen und die Operatoren zuzugreifen, die von der**-Ausdruckssprache bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f2f3c-123">To access the functions, the casts, and the operators that the [!INCLUDE[ssIS](../../includes/ssis-md.md)] expression language provides, expand **Mathematical Functions**, **String Functions**, **Date/Time Functions**, **NULL Functions**, **Type Casts**, and **Operators**.</span></span>  
  
    -   <span data-ttu-id="f2f3c-124">Um einen Ausdruck im **Ausdrucks-Generator**zu erstellen oder zu ändern, ziehen Sie die Variablen, Spalten, Funktionen, Operatoren und Umwandlungen in das Feld **Ausdruck** oder geben den Ausdruck im Feld ein.</span><span class="sxs-lookup"><span data-stu-id="f2f3c-124">To build or change an expression in the **Expression Builder**, drag variables, columns, functions, operators, and casts to the **Expression** box, or type the expression in the box.</span></span>  
  
    -   <span data-ttu-id="f2f3c-125">Klicken Sie im **Ausdrucks-Generator** auf **Ausdruck auswerten**, um das Auswertungsergebnis des Ausdrucks anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f2f3c-125">To view the evaluation result of the expression, click **Evaluate Expression** in the **Expression Builder**.</span></span>  
  
         <span data-ttu-id="f2f3c-126">Wenn der Ausdruck ungültig ist, wird eine Warnung angezeigt, in der die Syntaxfehler im Ausdruck beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="f2f3c-126">If the expression is not valid, an alert appears that describes the syntax errors in the expression.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="f2f3c-127">Die Auswertung eines Ausdrucks weist der Eigenschaft das Auswertungsergebnis nicht zu.</span><span class="sxs-lookup"><span data-stu-id="f2f3c-127">Evaluating an expression does not assign the evaluation result to the property.</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f2f3c-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f2f3c-128">See Also</span></span>  
 <span data-ttu-id="f2f3c-129">[Integration Services-Ausdrücke &#40;SSIS&#41;](integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="f2f3c-129">[Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md) </span></span>  
 <span data-ttu-id="f2f3c-130">[Verwenden von Eigenschaftsausdrücken in Paketen](use-property-expressions-in-packages.md) </span><span class="sxs-lookup"><span data-stu-id="f2f3c-130">[Use Property Expressions in Packages](use-property-expressions-in-packages.md) </span></span>  
 <span data-ttu-id="f2f3c-131">[Integration Services-Pakete &#40;SSIS&#41;](../integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="f2f3c-131">[Integration Services &#40;SSIS&#41; Packages](../integration-services-ssis-packages.md) </span></span>  
 <span data-ttu-id="f2f3c-132">[Integration Services-Container](../control-flow/integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="f2f3c-132">[Integration Services Containers](../control-flow/integration-services-containers.md) </span></span>  
 <span data-ttu-id="f2f3c-133">[Integration Services-Tasks](../control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="f2f3c-133">[Integration Services Tasks](../control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="f2f3c-134">[Integration Services-Ereignishandler &#40;SSIS&#41;](../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="f2f3c-134">[Integration Services &#40;SSIS&#41; Event Handlers](../integration-services-ssis-event-handlers.md) </span></span>  
 <span data-ttu-id="f2f3c-135">[Integration Services (SSIS) Connections (Integration Services-Verbindungen (SSIS))](../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="f2f3c-135">[Integration Services &#40;SSIS&#41; Connections](../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="f2f3c-136">Integration Services-Protokollierung &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="f2f3c-136">Integration Services &#40;SSIS&#41; Logging</span></span>](../performance/integration-services-ssis-logging.md)  
  
  
