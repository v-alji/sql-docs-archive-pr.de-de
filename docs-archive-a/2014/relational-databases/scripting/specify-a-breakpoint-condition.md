---
title: Angeben einer Breakpointbedingung
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoint conditions
ms.assetid: b43d8a2b-99a3-4fb7-8848-99c042ea7ef7
author: rothja
ms.author: jroth
ms.openlocfilehash: 659b6ca1149eb8f0412efbe2adbaf4c1ffce59d8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717797"
---
# <a name="specify-a-breakpoint-condition"></a><span data-ttu-id="c58bc-102">Angeben einer Breakpointbedingung</span><span class="sxs-lookup"><span data-stu-id="c58bc-102">Specify a Breakpoint Condition</span></span>
  <span data-ttu-id="c58bc-103">Eine Breakpointbedingung ist ein [!INCLUDE[tsql](../../includes/tsql-md.md)] -Ausdruck, der vom Debugger ausgewertet wird, wenn der Breaktpoint erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="c58bc-103">A breakpoint condition is a [!INCLUDE[tsql](../../includes/tsql-md.md)] expression that is evaluated by the debugger when the breakpoint is reached.</span></span> <span data-ttu-id="c58bc-104">Wenn die Bedingungen erfüllt ist und eine angegebene Trefferanzahl erreicht ist, unterbricht der Debugger die Ausführung, oder er führt die für den Breakpoint angegebene Aktion aus.</span><span class="sxs-lookup"><span data-stu-id="c58bc-104">If the condition is satisfied and any specified hit count reached, the debugger either breaks or performs the action specified for the breakpoint.</span></span>  
  
## <a name="specifying-conditions"></a><span data-ttu-id="c58bc-105">Angeben von Bedingungen</span><span class="sxs-lookup"><span data-stu-id="c58bc-105">Specifying Conditions</span></span>  
 <span data-ttu-id="c58bc-106">Der angegebene Ausdruck muss ein gültiger Transact-SQL-Ausdruck sein, der zu einem booleschen Wert ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="c58bc-106">The expression specified must be a valid Transact-SQL expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="c58bc-107">Weitere Informationen finden Sie unter [Expressions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/expressions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c58bc-107">For more information, see [Expressions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/expressions-transact-sql).</span></span>  
  
 <span data-ttu-id="c58bc-108">Wenn Sie eine Breakpointbedingung mit ungültiger Syntax angeben, wird sofort eine Warnmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c58bc-108">If you specify a breakpoint condition with invalid syntax, a warning message appears immediately.</span></span> <span data-ttu-id="c58bc-109">Wenn Sie eine Bedingung mit gültiger Syntax, jedoch ungültiger Semantik angeben, wird beim ersten Erreichen des Breakpoints eine Warnmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c58bc-109">If you specify a condition with valid syntax but invalid semantics, a warning message is displayed the first time the breakpoint is hit.</span></span> <span data-ttu-id="c58bc-110">In jedem Fall unterbricht der Debugger die Ausführung, wenn der ungültige Breakpoint erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="c58bc-110">In either case, the debugger breaks execution when the invalid breakpoint is hit.</span></span>  
  
#### <a name="to-specify-a-condition"></a><span data-ttu-id="c58bc-111">So geben Sie eine Bedingung an</span><span class="sxs-lookup"><span data-stu-id="c58bc-111">To Specify a Condition</span></span>  
  
1.  <span data-ttu-id="c58bc-112">Klicken Sie im Editor-Fenster mit der rechten Maustaste auf das Breakpointsymbol, und klicken Sie dann im Kontextmenü auf **Bedingung** .</span><span class="sxs-lookup"><span data-stu-id="c58bc-112">In the editor window, right-click the breakpoint glyph, and then click **Condition** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="c58bc-113">Oder</span><span class="sxs-lookup"><span data-stu-id="c58bc-113">-or-</span></span>  
  
     <span data-ttu-id="c58bc-114">Klicken Sie im **Breakpointfenster** mit der rechten Maustaste auf das Breakpointsymbol, und klicken Sie dann im Kontextmenü auf **Bedingung** .</span><span class="sxs-lookup"><span data-stu-id="c58bc-114">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Condition** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="c58bc-115">Geben Sie im Dialogfeld **Haltepunktbedingung** einen gültigen booleschen Ausdruck im Feld **Bedingung** ein.</span><span class="sxs-lookup"><span data-stu-id="c58bc-115">In the **Breakpoint Condition** dialog box, enter a valid Boolean expression in the **Condition** box.</span></span>  
  
3.  <span data-ttu-id="c58bc-116">Wählen Sie **ist "true** " aus, wenn Sie unterbrechen möchten, wenn der Ausdruck zu ausgewertet `true` wird, oder wenn Sie **sich geändert haben** , wenn der Wert des Ausdrucks geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="c58bc-116">Choose **Is true** if you want to break when the expression evaluates to `true`, or choose **Has changed** if you want to break when the value of the expression has changed.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c58bc-117">Der Debugger wertet den booleschen Ausdruck erst aus, wenn der Breakpoint das erste Mal erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="c58bc-117">The debugger does not evaluate the Boolean expression until the first time the breakpoint is reached.</span></span> <span data-ttu-id="c58bc-118">Wenn Sie **wurde geändert**auswählen, interpretiert der Debugger die erste Auswertung nicht als Änderung. Daher wird die Ausführung nicht bei der ersten Auswertung unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="c58bc-118">If you choose **Has changed**, the debugger does not consider the first evaluation to be a change, so the debugger will not break on the first evaluation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c58bc-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c58bc-119">See Also</span></span>  
 <span data-ttu-id="c58bc-120">[Angeben einer Treffer Anzahl](specify-a-hit-count.md) </span><span class="sxs-lookup"><span data-stu-id="c58bc-120">[Specify a Hit Count](specify-a-hit-count.md) </span></span>  
 [<span data-ttu-id="c58bc-121">Angeben einer Breakpointaktion</span><span class="sxs-lookup"><span data-stu-id="c58bc-121">Specify a Breakpoint Action</span></span>](specify-a-breakpoint-action.md)  
