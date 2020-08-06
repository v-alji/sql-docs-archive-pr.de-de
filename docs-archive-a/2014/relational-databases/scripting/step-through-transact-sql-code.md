---
title: Schrittweises Durchlaufen von Transact-SQL-Code
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, debugging code
- Transact-SQL debugger, step over
- Transact-SQL debugger, step out
- Transact-SQL debugger, step into
ms.assetid: e09079b8-c4c9-42b4-821b-4ce81a98a086
author: rothja
ms.author: jroth
ms.openlocfilehash: 48cb307130c65729640864a26bdf1dfaf344b32b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620802"
---
# <a name="step-through-transact-sql-code"></a><span data-ttu-id="f8b56-102">Schrittweises Durchlaufen von Transact-SQL-Code</span><span class="sxs-lookup"><span data-stu-id="f8b56-102">Step Through Transact-SQL Code</span></span>
  <span data-ttu-id="f8b56-103">Der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger ermöglicht es Ihnen, zu bestimmen, welche [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen in einem [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor-Fenster ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f8b56-103">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger enables you to control which [!INCLUDE[tsql](../../includes/tsql-md.md)] statements are run in a [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window.</span></span> <span data-ttu-id="f8b56-104">Sie können den Debugger bei einzelnen Anweisungen unterbrechen und dann den Status der Codeelemente an diesem Punkt anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f8b56-104">You can pause the debugger on individual statements and then view the state of the code elements at that point.</span></span>  
  
## <a name="breakpoints"></a><span data-ttu-id="f8b56-105">Breakpoints</span><span class="sxs-lookup"><span data-stu-id="f8b56-105">Breakpoints</span></span>  
 <span data-ttu-id="f8b56-106">Ein Breakpoint signalisiert dem Debugger, die Ausführung bei einer bestimmten [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="f8b56-106">A breakpoint signals the debugger to pause execution on a specific [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="f8b56-107">Weitere Informationen über Breakpoints finden Sie unter "Verwenden von Transact-SQL-Breakpoints".</span><span class="sxs-lookup"><span data-stu-id="f8b56-107">For more information about breakpoints, see Using Transact-SQL Breakpoints.</span></span>  
  
## <a name="controlling-statement-execution"></a><span data-ttu-id="f8b56-108">Steuern der Anweisungsausführung</span><span class="sxs-lookup"><span data-stu-id="f8b56-108">Controlling Statement Execution</span></span>  
 <span data-ttu-id="f8b56-109">Im [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger können Sie die folgenden Optionen für das Ausführen der aktuellen Anweisung im [!INCLUDE[tsql](../../includes/tsql-md.md)] -Code angeben:</span><span class="sxs-lookup"><span data-stu-id="f8b56-109">In the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger, you can specify the following options for executing from the current statement in [!INCLUDE[tsql](../../includes/tsql-md.md)] code:</span></span>  
  
-   <span data-ttu-id="f8b56-110">Den Vorgang bis zum nächsten Breakpoint ausführen</span><span class="sxs-lookup"><span data-stu-id="f8b56-110">Run to the next breakpoint.</span></span>  
  
-   <span data-ttu-id="f8b56-111">Einen Einzelschritt in die nächste Anweisung ausführen</span><span class="sxs-lookup"><span data-stu-id="f8b56-111">Step into the next statement.</span></span>  
  
     <span data-ttu-id="f8b56-112">Wenn die nächste Anweisung eine gespeicherte [!INCLUDE[tsql](../../includes/tsql-md.md)] -Prozedur, eine Funktion oder einen Trigger aufruft, zeigt der Debugger ein neues Abfrage-Editor-Fenster an, das den Code des Moduls enthält.</span><span class="sxs-lookup"><span data-stu-id="f8b56-112">If the next statement invokes a [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedure, function, or trigger, the debugger displays a new Query Editor window that contains the code of the module.</span></span> <span data-ttu-id="f8b56-113">Das Fenster befindet sich im Debuggingmodus, und die Ausführung hält bei der ersten Anweisung im Modul an.</span><span class="sxs-lookup"><span data-stu-id="f8b56-113">The window is in debug mode, and execution pauses on the first statement in the module.</span></span> <span data-ttu-id="f8b56-114">Sie können sich dann durch den Modulcode bewegen, indem Sie z. B. Breakpoints festlegen oder den Code schrittweise durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="f8b56-114">You can then move through the module code, for example, by setting breakpoints or stepping through the code.</span></span>  
  
-   <span data-ttu-id="f8b56-115">Einen Einzelschritt in die nächste Anweisung überspringen</span><span class="sxs-lookup"><span data-stu-id="f8b56-115">Step over the next statement.</span></span>  
  
     <span data-ttu-id="f8b56-116">Die nächste Anweisung wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f8b56-116">The next statement is executed.</span></span> <span data-ttu-id="f8b56-117">Wenn die Anweisung jedoch eine gespeicherte Prozedur, eine Funktion oder einen Trigger aufruft, wird der Modulcode bis zum Ende ausgeführt, und die Ergebnisse werden an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f8b56-117">However, if the statement invokes a stored procedure, function, or trigger, the module code runs until it finishes, and the results are returned to the calling code.</span></span> <span data-ttu-id="f8b56-118">Wenn Sie sicher sind, dass in der gespeicherten Prozedur keine Fehler vorliegen, können Sie sie überspringen.</span><span class="sxs-lookup"><span data-stu-id="f8b56-118">If you are sure there are no errors in a stored procedure, you can step over it.</span></span> <span data-ttu-id="f8b56-119">Die Ausführung hält bei der Anweisung an, die dem Aufruf der gespeicherten Prozedur, der Funktion oder dem Trigger folgt.</span><span class="sxs-lookup"><span data-stu-id="f8b56-119">Execution pauses on the statement that follows the call to the stored procedure, function, or trigger.</span></span>  
  
-   <span data-ttu-id="f8b56-120">Eine gespeicherte Prozedur, eine Funktion oder einen Trigger bis zum Rücksprung ausführen</span><span class="sxs-lookup"><span data-stu-id="f8b56-120">Step out of a stored procedure, function, or trigger.</span></span>  
  
     <span data-ttu-id="f8b56-121">Die Ausführung hält bei der Anweisung an, die dem Aufruf der gespeicherten Prozedur, der Funktion oder dem Trigger folgt.</span><span class="sxs-lookup"><span data-stu-id="f8b56-121">Execution pauses on the statement that follows the call to the stored procedure, function, or trigger.</span></span>  
  
-   <span data-ttu-id="f8b56-122">Den Vorgang von der aktuellen Position bis zur aktuellen Position des Zeigers ausführen und alle Breakpoints ignorieren</span><span class="sxs-lookup"><span data-stu-id="f8b56-122">Run from the current location to the current location of the pointer, and ignore all breakpoints.</span></span>  
  
 <span data-ttu-id="f8b56-123">Die folgende Tabelle enthält die verschiedenen Möglichkeiten, mit denen Sie bestimmen können, wie Anweisungen im [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f8b56-123">The following table lists the various ways in which you can control how statements execute in the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger.</span></span>  
  
|<span data-ttu-id="f8b56-124">Action</span><span class="sxs-lookup"><span data-stu-id="f8b56-124">Action</span></span>|<span data-ttu-id="f8b56-125">Verfahren</span><span class="sxs-lookup"><span data-stu-id="f8b56-125">Procedure</span></span>|  
|------------|---------------|  
|<span data-ttu-id="f8b56-126">Ausführen aller Anweisungen von der aktuellen Anweisung bis zum nächsten Breakpoint</span><span class="sxs-lookup"><span data-stu-id="f8b56-126">Run all statements from the current statement to the next breakpoint</span></span>|<span data-ttu-id="f8b56-127">Klicken Sie im Menü **Debuggen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f8b56-127">On the **Debug** menu, click **Continue**.</span></span><br /><br /> <span data-ttu-id="f8b56-128">Klicken Sie auf der Symbolleiste **Debuggen** auf die Schaltfläche **weiter** .</span><span class="sxs-lookup"><span data-stu-id="f8b56-128">On the **Debug** toolbar, click the **Continue** button.</span></span>|  
|<span data-ttu-id="f8b56-129">Ausführen eines Einzelschritts in die nächste Anweisung oder in das nächste Modul</span><span class="sxs-lookup"><span data-stu-id="f8b56-129">Step into the next statement or module</span></span>|<span data-ttu-id="f8b56-130">Klicken Sie im Menü **Debuggen** auf Einzel **Schritt**.</span><span class="sxs-lookup"><span data-stu-id="f8b56-130">On the **Debug** menu, click **Step Into**.</span></span><br /><br /> <span data-ttu-id="f8b56-131">Klicken Sie auf der Symbolleiste **Debuggen** auf die Schaltfläche Einzel **Schritt** .</span><span class="sxs-lookup"><span data-stu-id="f8b56-131">On the **Debug** toolbar, click the **Step Into** button.</span></span><br /><br /> <span data-ttu-id="f8b56-132">Drücken Sie F11.</span><span class="sxs-lookup"><span data-stu-id="f8b56-132">Press F11.</span></span>|  
|<span data-ttu-id="f8b56-133">Überspringen der nächsten Anweisung oder des nächsten Moduls</span><span class="sxs-lookup"><span data-stu-id="f8b56-133">Step over the next statement or module</span></span>|<span data-ttu-id="f8b56-134">Klicken Sie im Menü **Debuggen** auf **Prozedurschritt**.</span><span class="sxs-lookup"><span data-stu-id="f8b56-134">On the **Debug** menu, click **Step Over**.</span></span><br /><br /> <span data-ttu-id="f8b56-135">Klicken Sie auf der Symbolleiste **Debuggen** auf die Schaltfläche Prozedur **Schritt** .</span><span class="sxs-lookup"><span data-stu-id="f8b56-135">On the **Debug** toolbar, click the **Step Over** button.</span></span><br /><br /> <span data-ttu-id="f8b56-136">Drücken Sie F10.</span><span class="sxs-lookup"><span data-stu-id="f8b56-136">Press F10.</span></span>|  
|<span data-ttu-id="f8b56-137">Ausführen eines Moduls bis Rücksprung</span><span class="sxs-lookup"><span data-stu-id="f8b56-137">Step out of a module</span></span>|<span data-ttu-id="f8b56-138">Klicken Sie im Menü **Debuggen** auf Rück **Sprung**.</span><span class="sxs-lookup"><span data-stu-id="f8b56-138">On the **Debug** menu, click **Step Out**.</span></span><br /><br /> <span data-ttu-id="f8b56-139">Klicken Sie auf der Symbolleiste **Debuggen** auf die Schaltfläche Rück **Sprung** .</span><span class="sxs-lookup"><span data-stu-id="f8b56-139">On the **Debug** toolbar, click the **Step Out** button.</span></span><br /><br /> <span data-ttu-id="f8b56-140">Drücken Sie UMSCHALT+F11.</span><span class="sxs-lookup"><span data-stu-id="f8b56-140">Press SHIFT+F11.</span></span>|  
|<span data-ttu-id="f8b56-141">Ausführen bis zur aktuellen Cursorposition</span><span class="sxs-lookup"><span data-stu-id="f8b56-141">Run to the current cursor location</span></span>|<span data-ttu-id="f8b56-142">Klicken Sie mit der rechten Maustaste auf das Abfrage-Editor-Fenster, und klicken Sie dann auf **Ausführen bis Cursorposition**.</span><span class="sxs-lookup"><span data-stu-id="f8b56-142">Right-click in the Query Editor window, and then click **Run To Cursor**.</span></span><br /><br /> <span data-ttu-id="f8b56-143">Drücken Sie STRG+F10.</span><span class="sxs-lookup"><span data-stu-id="f8b56-143">Press CTRL+F10.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8b56-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8b56-144">See Also</span></span>  
 [<span data-ttu-id="f8b56-145">Transact-SQL-Debuggerinformationen</span><span class="sxs-lookup"><span data-stu-id="f8b56-145">Transact-SQL Debugger Information</span></span>](transact-sql-debugger-information.md)  
  
  
