---
title: Angeben einer Trefferanzahl
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- vs.debug.breakpt.hitcount
helpviewer_keywords:
- Transact-SQL debugger, breakpoint hit count
ms.assetid: 24836939-94ed-4e57-aa85-5d6938d859e4
author: rothja
ms.author: jroth
ms.openlocfilehash: 34c75e990bce1ea5e64c0b45f7acbcaa52fc3c40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620267"
---
# <a name="specify-a-hit-count"></a><span data-ttu-id="51b29-102">Angeben einer Trefferanzahl</span><span class="sxs-lookup"><span data-stu-id="51b29-102">Specify a Hit Count</span></span>
  <span data-ttu-id="51b29-103">Die Breakpoint-Trefferanzahl bildet einen Leistungsindikator, der bei jedem Erreichen des Breakpoints vom [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger inkrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="51b29-103">A breakpoint hit count is a counter that is incremented by the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger each time the breakpoint is reached.</span></span> <span data-ttu-id="51b29-104">Wenn die angegebene Trefferanzahl erreicht ist und alle angegebenen Breakpointbedingungen erfüllt sind, führt der Debugger die für den Breakpoint angegebene Aktion aus.</span><span class="sxs-lookup"><span data-stu-id="51b29-104">If the specified hit count is reached and any specified breakpoint condition is satisfied, the debugger performs the action specified for the breakpoint.</span></span>  
  
## <a name="hit-count-considerations"></a><span data-ttu-id="51b29-105">Überlegungen zur Trefferanzahl</span><span class="sxs-lookup"><span data-stu-id="51b29-105">Hit Count Considerations</span></span>  
 <span data-ttu-id="51b29-106">Standardmäßig wird die Ausführung stets unterbrochen, wenn ein Breakpoint erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="51b29-106">By default, execution breaks every time a breakpoint is hit.</span></span> <span data-ttu-id="51b29-107">Folgende Optionen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="51b29-107">You can choose between the following options:</span></span>  
  
-   <span data-ttu-id="51b29-108">Immer anhalten (Standard).</span><span class="sxs-lookup"><span data-stu-id="51b29-108">Break always (the default).</span></span>  
  
-   <span data-ttu-id="51b29-109">Anhalten, wenn die Trefferanzahl gleich einem angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="51b29-109">Break when the hit count equals a specified value.</span></span>  
  
-   <span data-ttu-id="51b29-110">Anhalten, wenn die Trefferanzahl ein Vielfaches ist von einem angegebenen Wert.</span><span class="sxs-lookup"><span data-stu-id="51b29-110">Break when the hit count equals a multiple of a specified value.</span></span>  
  
-   <span data-ttu-id="51b29-111">Anhalten, wenn die Trefferanzahl größer oder gleich einem angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="51b29-111">Break when the hit count is greater than or equal to a specified value.</span></span>  
  
 <span data-ttu-id="51b29-112">Die Breakpoint-Trefferanzahlen werden innerhalb einer Debugsitzung inkrementiert.</span><span class="sxs-lookup"><span data-stu-id="51b29-112">Breakpoint hit counts are incremented within the scope of a debugging session.</span></span> <span data-ttu-id="51b29-113">Zu Beginn jeder Debugsitzung werden alle Trefferanzahlen auf 0 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="51b29-113">All hit counts are set to zero at the start of each debugging session.</span></span>  
  
 <span data-ttu-id="51b29-114">Wenn Sie die Häufigkeit nachverfolgen möchten, mit der ein Breakpoint erreicht wurde, ohne die Ausführung zu unterbrechen, geben Sie eine Trefferanzahl mit sehr hohen Wert an, damit beim Breakpoint nie eine Unterbrechung eintritt.</span><span class="sxs-lookup"><span data-stu-id="51b29-114">If you want to track how many times a breakpoint is hit without having the breakpoint break execution, specify a hit count with a very high value so the breakpoint never breaks.</span></span>  
  
 <span data-ttu-id="51b29-115">Die Standardaktion für einen Breakpoint besteht darin, die Ausführung zu unterbrechen, wenn die Trefferanzahl- und die Breakpointbedingung erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="51b29-115">The default action for a breakpoint is to break execution when both the hit count and breakpoint condition have been satisfied.</span></span> <span data-ttu-id="51b29-116">Informationen zum Angeben anderer Aktionen finden Sie unter [Angeben einer Breakpointaktion](specify-a-breakpoint-action.md).</span><span class="sxs-lookup"><span data-stu-id="51b29-116">For information about specifying other actions, see [Specify a Breakpoint Action](specify-a-breakpoint-action.md).</span></span>  
  
#### <a name="to-specify-a-hit-count"></a><span data-ttu-id="51b29-117">So geben Sie eine Trefferanzahl an</span><span class="sxs-lookup"><span data-stu-id="51b29-117">To Specify a Hit Count</span></span>  
  
1.  <span data-ttu-id="51b29-118">Klicken Sie im Editor-Fenster mit der rechten Maustaste auf das Breakpointsymbol, und klicken Sie dann im Kontextmenü auf **Trefferanzahl** .</span><span class="sxs-lookup"><span data-stu-id="51b29-118">In the editor window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="51b29-119">Oder</span><span class="sxs-lookup"><span data-stu-id="51b29-119">-or-</span></span>  
  
     <span data-ttu-id="51b29-120">Klicken Sie im Fenster **Breakpoints** mit der rechten Maustaste auf das Breakpointsymbol, und klicken Sie dann im Kontextmenü auf **Trefferanzahl** .</span><span class="sxs-lookup"><span data-stu-id="51b29-120">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="51b29-121">Wählen Sie im Dialogfeld **Trefferanzahl für Haltepunkt** im Feld **Wenn der Haltepunkt erreicht wird** das gewünschte Verhalten aus.</span><span class="sxs-lookup"><span data-stu-id="51b29-121">In the **Breakpoint Hit Count** dialog box, select the behavior you want from the **When the breakpoint is hit** box.</span></span>  
  
     <span data-ttu-id="51b29-122">Wenn Sie eine andere Einstellung als **Immer anhalten**auswählen, wird rechts neben der Liste ein Textfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="51b29-122">If you choose any setting other than **Break Always**, a text box appears to the right of the list.</span></span> <span data-ttu-id="51b29-123">Geben Sie in diesem Textfeld die gewünschte Trefferanzahl als ganze Zahl ein.</span><span class="sxs-lookup"><span data-stu-id="51b29-123">Enter an integer in the text box to specify the hit count you want.</span></span>  
  
3.  <span data-ttu-id="51b29-124">Klicken Sie auf **OK** , um die Änderungen zu implementieren, oder auf **Abbrechen** , um den Vorgang zu beenden, ohne die Änderungen zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="51b29-124">Click **OK** to implement the changes, or **Cancel** to exit without applying the changes.</span></span>  
  
#### <a name="to-view-or-reset-the-current-hit-count"></a><span data-ttu-id="51b29-125">So zeigen Sie die aktuelle Trefferanzahl an oder setzen diese zurück</span><span class="sxs-lookup"><span data-stu-id="51b29-125">To View or Reset the Current Hit Count</span></span>  
  
1.  <span data-ttu-id="51b29-126">Klicken Sie im Editor-Fenster mit der rechten Maustaste auf das Breakpointsymbol, und klicken Sie dann im Kontextmenü auf **Trefferanzahl** .</span><span class="sxs-lookup"><span data-stu-id="51b29-126">In the editor window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
     <span data-ttu-id="51b29-127">Oder</span><span class="sxs-lookup"><span data-stu-id="51b29-127">-or-</span></span>  
  
     <span data-ttu-id="51b29-128">Klicken Sie im Fenster **Breakpoints** mit der rechten Maustaste auf das Breakpointsymbol, und klicken Sie dann im Kontextmenü auf **Trefferanzahl** .</span><span class="sxs-lookup"><span data-stu-id="51b29-128">In the **Breakpoints** window, right-click the breakpoint glyph, and then click **Hit Count** on the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="51b29-129">Im Dialogfeld **Trefferanzahl für Haltepunkt** wird direkt über der Schaltfläche **Zurücksetzen** der Wert **Aktuelle Trefferanzahl** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="51b29-129">In the **Breakpoint Hit Count** dialog box, the **Current hit count:** is displayed just above the **Reset** button.</span></span>  
  
3.  <span data-ttu-id="51b29-130">Klicken Sie auf **Zurücksetzen** , wenn Sie die aktuelle Trefferanzahl auf 0 festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="51b29-130">Click **Reset** if you want to set the current hit count to zero.</span></span>  
  
4.  <span data-ttu-id="51b29-131">Klicken Sie auf **OK** oder **Abbrechen** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="51b29-131">Click **OK** or **Cancel** to exit the dialog.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51b29-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51b29-132">See Also</span></span>  
 [<span data-ttu-id="51b29-133">Angeben einer Breakpointbedingung</span><span class="sxs-lookup"><span data-stu-id="51b29-133">Specify a Breakpoint Condition</span></span>](specify-a-breakpoint-condition.md)  
  
  
