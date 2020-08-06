---
title: Verwenden eines Ausdrucks in einer Datenfluss Komponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- components [Integration Services], data flow
- expressions [Integration Services], data flow components
ms.assetid: 9181b998-d24a-41fb-bb3c-14eee34f910d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 653bf468d0af6d44c5abe7344fcc13f93f86b430
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718427"
---
# <a name="use-an-expression-in-a-data-flow-component"></a><span data-ttu-id="27577-102">Verwenden eines Ausdrucks in einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="27577-102">Use an Expression in a Data Flow Component</span></span>
  <span data-ttu-id="27577-103">In diesem Verfahren wird beschrieben, wie ein Ausdruck der Transformation für bedingtes Teilen oder der Transformation für abgeleitete Spalten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="27577-103">This procedure describes how to add an expression to the Conditional Split transformation or to the Derived Column transformation.</span></span> <span data-ttu-id="27577-104">Die Transformation für bedingtes Teilen verwendet Ausdrücke zum Definieren der Bedingungen, die Datenzeilen in eine Transformationsausgabe leiten, und die Transformation für abgeleitete Spalten verwendet Ausdrücke zum Definieren von Werten, die Spalten zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="27577-104">The Conditional Split transformation uses expressions to define the conditions that direct data rows to a transformation output, and the Derived Column transformation uses expressions to define values assigned to columns.</span></span>  
  
 <span data-ttu-id="27577-105">Um einen Ausdruck in einer Transformation zu implementieren, muss das Paket bereits mindestens einen Datenflusstask und eine Quelle einschließen.</span><span class="sxs-lookup"><span data-stu-id="27577-105">To implement an expression in a transformation, the package must already include at least one Data Flow task and a source.</span></span> <span data-ttu-id="27577-106">Weitere Informationen zum Hinzufügen von Elementen zu Paketen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="27577-106">For information about adding items to packages, see the following topics:</span></span>  
  
-   [<span data-ttu-id="27577-107">Hinzufügen oder Löschen eines Tasks oder Containers in einer Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="27577-107">Add or Delete a Task or a Container in a Control Flow</span></span>](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
    
  
-   [<span data-ttu-id="27577-108">Hinzufügen oder Löschen einer Komponente im Datenfluss</span><span class="sxs-lookup"><span data-stu-id="27577-108">Add or Delete a Component in a Data Flow</span></span>](data-flow/add-or-delete-a-component-in-a-data-flow.md)  
  
-   [<span data-ttu-id="27577-109">Verbinden von Komponenten in einem Datenfluss</span><span class="sxs-lookup"><span data-stu-id="27577-109">Connect Components in a Data Flow</span></span>](data-flow/connect-components-in-a-data-flow.md)  
  
### <a name="to-create-an-expression"></a><span data-ttu-id="27577-110">So erstellen Sie einen Ausdruck</span><span class="sxs-lookup"><span data-stu-id="27577-110">To create an expression</span></span>  
  
1.  <span data-ttu-id="27577-111">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="27577-111">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="27577-112">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="27577-112">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="27577-113">Klicken Sie im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer auf die Registerkarte **Ablaufsteuerung** , und klicken Sie dann auf den Datenflusstask mit dem Datenfluss, den Sie in einem Ausdruck implementieren möchten.</span><span class="sxs-lookup"><span data-stu-id="27577-113">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Control Flow** tab, and then click the Data Flow task that contains the data flow in which you want to implement an expression.</span></span>  
  
4.  <span data-ttu-id="27577-114">Klicken Sie auf die Registerkarte **Datenfluss** , und ziehen Sie dann aus der **Toolbox** die Transformation für bedingtes Teilen oder die Transformation für abgeleitete Spalten auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="27577-114">Click the **Data Flow** tab, and drag either a Conditional Split or Derived Column transformation from the **Toolbox** to the design surface.</span></span>  
  
5.  <span data-ttu-id="27577-115">Ziehen Sie den grünen Konnektor von der Quelle oder einer Transformation auf die Transformation für bedingtes Teilen oder abgeleitete Spalten.</span><span class="sxs-lookup"><span data-stu-id="27577-115">Drag the green connector from the source or a transformation to the Conditional Split or Derived Column transformation.</span></span>  
  
6.  <span data-ttu-id="27577-116">Doppelklicken Sie auf die Transformation, um ihr Dialogfeld zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="27577-116">Double-click the transformation to open its dialog box.</span></span>  
  
7.  <span data-ttu-id="27577-117">Erweitern Sie im linken Fenster die Option **Variablen** , um system- und benutzerdefinierte Variablen anzuzeigen, und erweitern Sie **Spalten** , um die Transformationseingabespalten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="27577-117">In the left pane, expand **Variables** to display system and user-defined variables, and expand **Columns** to display the transformation input columns.</span></span>  
  
8.  <span data-ttu-id="27577-118">Erweitern Sie im rechten Fenster die Option **Mathematische Funktionen**, **Zeichenfolgenfunktionen**, **Datums-/Uhrzeitfunktionen**, **NULL-Funktionen**, **Typumwandlungen**und **Operatoren** , um auf die Funktionen, die Umwandlungen und die Operatoren zuzugreifen, die von der Ausdrucksgrammatik bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="27577-118">In the right pane, expand **Mathematical Functions**, **String Functions**, **Date/Time Functions**, **NULL Functions**, **Type Casts**, and **Operators** to access the functions, the casts, and the operators that the expression grammar provides.</span></span>  
  
9. <span data-ttu-id="27577-119">Gehen Sie je nach Transformation zum Erstellen eines Ausdrucks wie folgt vor</span><span class="sxs-lookup"><span data-stu-id="27577-119">Depending on the transformation, do one of the following to build an expression:</span></span>  
  
    -   <span data-ttu-id="27577-120">Ziehen Sie im Dialogfeld **Transformations-Editor für bedingtes Teilen** die Variablen, Spalten, Funktionen, Operatoren und Umwandlungen in die Spalte **Bedingung** .</span><span class="sxs-lookup"><span data-stu-id="27577-120">In the **Conditional Split Transformation Editor** dialog box, drag variables, columns, functions, operators, and casts to the **Condition** column.</span></span> <span data-ttu-id="27577-121">Sie können den Ausdruck aber auch direkt in die Spalte **Bedingung** eingeben.</span><span class="sxs-lookup"><span data-stu-id="27577-121">Alternatively, you can type an expression directly in the **Condition** column.</span></span>  
  
    -   <span data-ttu-id="27577-122">Ziehen Sie im Dialogfeld **Transformations-Editor für abgeleitete Spalten** die Variablen, Spalten, Funktionen, Operatoren und Umwandlungen in die Spalte **Ausdruck** .</span><span class="sxs-lookup"><span data-stu-id="27577-122">In the **Derived Column Transformation Editor** dialog box, drag variables, columns, functions, operators, and casts to the **Expression** column.</span></span> <span data-ttu-id="27577-123">Sie können den Ausdruck aber auch direkt in die Spalte **Ausdruck** eingeben.</span><span class="sxs-lookup"><span data-stu-id="27577-123">Alternatively, you can type an expression directly in the **Expression** column.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="27577-124"> Wenn Sie den Fokus von der Spalte **Bedingung** oder **Ausdruck** entfernen, kann der Ausdruckstext hervorgehoben dargestellt werden, was auf eine falsche Ausdruckssyntax hinweist.</span><span class="sxs-lookup"><span data-stu-id="27577-124">When you remove the focus from the **Condition** column or the **Expression** column, the expression text might be highlighted to indicate that the expression syntax is incorrect.</span></span>  
  
10. <span data-ttu-id="27577-125">Klicken Sie auf **OK**, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="27577-125">Click **OK** to exit the dialog box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="27577-126">Wenn der Ausdruck ungültig ist, wird eine Warnung angezeigt, die die Syntaxfehler im Ausdruck beschreibt.</span><span class="sxs-lookup"><span data-stu-id="27577-126">If the expression is not valid, an alert appears describing the syntax errors in the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27577-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27577-127">See Also</span></span>  
 <span data-ttu-id="27577-128">[Integration Services &#40;SSIS-&#41; Ausdrücke](expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="27577-128">[Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md) </span></span>  
 <span data-ttu-id="27577-129">[Transformation für bedingtes Teilen](data-flow/transformations/conditional-split-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="27577-129">[Conditional Split Transformation](data-flow/transformations/conditional-split-transformation.md) </span></span>  
 <span data-ttu-id="27577-130">[Derived Column Transformation](data-flow/transformations/derived-column-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="27577-130">[Derived Column Transformation](data-flow/transformations/derived-column-transformation.md) </span></span>  
 <span data-ttu-id="27577-131">[Datenflusstask](control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="27577-131">[Data Flow Task](control-flow/data-flow-task.md) </span></span>  
 [<span data-ttu-id="27577-132">Datenfluss</span><span class="sxs-lookup"><span data-stu-id="27577-132">Data Flow</span></span>](data-flow/data-flow.md)  
  
  
