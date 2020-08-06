---
title: Fenster 'Breakpoints'
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Breakpoints Window [Transact-SQL]
ms.assetid: bad88d10-fdd5-4d3d-b5ea-a4f063847485
author: rothja
ms.author: jroth
ms.openlocfilehash: 077d501e581ed5baaac45cc6bbbb34e0040730e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620793"
---
# <a name="breakpoints-window"></a><span data-ttu-id="a8d1a-102">Fenster 'Breakpoints'</span><span class="sxs-lookup"><span data-stu-id="a8d1a-102">Breakpoints Window</span></span>
  <span data-ttu-id="a8d1a-103">Im Fenster **Breakpoints** werden alle Breakpoints aufgelistet, die im aktuellen [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-103">The **Breakpoints** window lists all the breakpoints that are set in the current [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span> <span data-ttu-id="a8d1a-104">Um die Breakpoints zu verwalten, verwenden Sie die Symbolleiste im Fenster **Breakpoints** .</span><span class="sxs-lookup"><span data-stu-id="a8d1a-104">To manage the breakpoints, use the toolbar in the **Breakpoints** window.</span></span> <span data-ttu-id="a8d1a-105">Breakpoints sind Positionen im Code, an denen die Ausführung im Debugmodus angehalten wird, sodass Sie Debugdaten anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-105">Breakpoints are locations in the code where execution pauses in debug mode so that you can view debugging data.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="a8d1a-106">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="a8d1a-106">Task List</span></span>  
 <span data-ttu-id="a8d1a-107">**So greifen Sie auf das Fenster Breakpoints zu**</span><span class="sxs-lookup"><span data-stu-id="a8d1a-107">**To access the Breakpoints window**</span></span>  
  
-   <span data-ttu-id="a8d1a-108">Klicken Sie im Menü **Debuggen** auf **Fenster**und dann auf **Breakpoints**.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-108">On the **Debug** menu, click **Windows**, and then click **Breakpoints**.</span></span>  
  
## <a name="breakpoints-window-columns"></a><span data-ttu-id="a8d1a-109">Spalten des Fensters 'Breakpoints'</span><span class="sxs-lookup"><span data-stu-id="a8d1a-109">Breakpoints Window Columns</span></span>  
 <span data-ttu-id="a8d1a-110">Standardmäßig listet das Fenster **Breakpoints** die folgenden Spalten auf.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-110">By default, the **Breakpoints** window lists the following columns.</span></span>  
  
 <span data-ttu-id="a8d1a-111">**Name**</span><span class="sxs-lookup"><span data-stu-id="a8d1a-111">**Name**</span></span>  
 <span data-ttu-id="a8d1a-112">Zeigt den Namen des Breakpoints an.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-112">Displays the name of the breakpoint.</span></span> <span data-ttu-id="a8d1a-113">Breakpointnamen werden vom Debugger bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-113">Breakpoint names are provided by the debugger.</span></span> <span data-ttu-id="a8d1a-114">Dieser Name umfasst den Namen aus dem Abfrage-Editor-Fenster der Datenbank-Engine, die den Breakpoint enthält, und die Zeilennummer im Abfrage-Editor, auf die der Breakpoint festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-114">This name includes the name of Database Engine Query Editor window that contains the breakpoint, and the line number in the Query Editor on which the breakpoint is set.</span></span>  
  
 <span data-ttu-id="a8d1a-115">**Condition**</span><span class="sxs-lookup"><span data-stu-id="a8d1a-115">**Condition**</span></span>  
 <span data-ttu-id="a8d1a-116">Zeigt **(Keine Bedingung)** an.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-116">Displays **(no condition)**.</span></span> <span data-ttu-id="a8d1a-117">Der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger unterstützt das Festlegen von Breakpointbedingungen nicht.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-117">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support setting breakpoint conditions.</span></span>  
  
 <span data-ttu-id="a8d1a-118">**Trefferanzahl**</span><span class="sxs-lookup"><span data-stu-id="a8d1a-118">**Hit Count**</span></span>  
 <span data-ttu-id="a8d1a-119">Zeigt**Immer unterbrechen**an.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-119">Displays**breaks always**.</span></span>  
  
 <span data-ttu-id="a8d1a-120">Sie können die folgenden Spalten hinzufügen und entfernen, indem Sie sie in der Liste **Spalten** auswählen.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-120">You can add and remove the following columns by selecting them on the **Columns** list.</span></span>  
  
 <span data-ttu-id="a8d1a-121">**Filter**</span><span class="sxs-lookup"><span data-stu-id="a8d1a-121">**Filter**</span></span>  
 <span data-ttu-id="a8d1a-122">Zeigt **(Keine)** an.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-122">Displays **(none)**.</span></span> <span data-ttu-id="a8d1a-123">Der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger unterstützt das Festlegen von Breakpointfiltern nicht.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-123">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support setting breakpoint filters.</span></span>  
  
 <span data-ttu-id="a8d1a-124">**Bei Treffer**</span><span class="sxs-lookup"><span data-stu-id="a8d1a-124">**When Hit**</span></span>  
 <span data-ttu-id="a8d1a-125">Zeigt **Unterbrechen**an.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-125">Displays **Break**.</span></span>  
  
 <span data-ttu-id="a8d1a-126">**Sprache**</span><span class="sxs-lookup"><span data-stu-id="a8d1a-126">**Language**</span></span>  
 <span data-ttu-id="a8d1a-127">Zeigt **Transact-SQL** für [!INCLUDE[tsql](../../includes/tsql-md.md)]an.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-127">Displays **Transact-SQL** for [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="a8d1a-128">**Function**</span><span class="sxs-lookup"><span data-stu-id="a8d1a-128">**Function**</span></span>  
 <span data-ttu-id="a8d1a-129">Zeigt die Nummer der Zeile an, auf der der Breakpoint festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-129">Displays the number of the line on which the breakpoint is set.</span></span>  
  
 <span data-ttu-id="a8d1a-130">**File**</span><span class="sxs-lookup"><span data-stu-id="a8d1a-130">**File**</span></span>  
 <span data-ttu-id="a8d1a-131">Zeigt den Namen der Quelldatei an, die den Breakpoint enthält, und die Nummer der Zeile, auf der der Breakpoint festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-131">Displays the name of the source file that contains the breakpoint, and the number of the line on which the breakpoint is set.</span></span>  
  
 <span data-ttu-id="a8d1a-132">**Adresse**</span><span class="sxs-lookup"><span data-stu-id="a8d1a-132">**Address**</span></span>  
 <span data-ttu-id="a8d1a-133">Der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger unterstützt diese Funktion nicht.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-133">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger does not support this feature.</span></span>  
  
 <span data-ttu-id="a8d1a-134">**Prozess**</span><span class="sxs-lookup"><span data-stu-id="a8d1a-134">**Process**</span></span>  
 <span data-ttu-id="a8d1a-135">Zeigt **[SQL]** an, um darauf hinzuweisen, dass es sich um einen [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Prozess handelt.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-135">Displays **[SQL]** to indicate that this is a [!INCLUDE[ssDE](../../includes/ssde-md.md)] process.</span></span> <span data-ttu-id="a8d1a-136">Danach folgt der Name der Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] , in der der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-136">This is followed by the name of the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] in which the code executes.</span></span>  
  
## <a name="breakpoints-window-toolbar"></a><span data-ttu-id="a8d1a-137">Symbolleiste des Fensters 'Breakpoints'</span><span class="sxs-lookup"><span data-stu-id="a8d1a-137">Breakpoints Window Toolbar</span></span>  
 <span data-ttu-id="a8d1a-138">Wenn das aktuelle [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor-Fenster aktive Breakpoints enthält, wird im Fenster **Breakpoints** eine Symbolleiste angezeigt, die zum Verwalten der Breakpoints verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-138">When the current [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window has active breakpoints, the **Breakpoints** window displays a toolbar that can be used to manage the breakpoints.</span></span>  
  
 <span data-ttu-id="a8d1a-139">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="a8d1a-139">**Delete**</span></span>  
 <span data-ttu-id="a8d1a-140">Löscht den ausgewählten Breakpoint.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-140">Deletes the selected breakpoint.</span></span>  
  
 <span data-ttu-id="a8d1a-141">**Alle Breakpoints löschen**</span><span class="sxs-lookup"><span data-stu-id="a8d1a-141">**Delete All Breakpoints**</span></span>  
 <span data-ttu-id="a8d1a-142">Löscht alle Breakpoints, die im Fenster **Breakpoints** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-142">Deletes all breakpoints that are displayed in the **Breakpoints** window.</span></span>  
  
 <span data-ttu-id="a8d1a-143">**Alle Breakpoints deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="a8d1a-143">**Disable All Breakpoints**</span></span>  
 <span data-ttu-id="a8d1a-144">Deaktiviert alle Breakpoints, sodass sie die Codeausführung nicht mehr anhalten; die Breakpoints werden jedoch beibehalten.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-144">Disables all breakpoints so that they no longer stop code execution; however, the breakpoints remain.</span></span> <span data-ttu-id="a8d1a-145">Wenn alle Breakpoints deaktiviert sind, wird diese Schaltfläche als **Breakpoints aktivieren**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-145">When all the breakpoints are disabled, this button becomes **Enable All Breakpoints**.</span></span>  
  
 <span data-ttu-id="a8d1a-146">**Breakpoints aktivieren**</span><span class="sxs-lookup"><span data-stu-id="a8d1a-146">**Enable All Breakpoints**</span></span>  
 <span data-ttu-id="a8d1a-147">Aktiviert alle Breakpoints, sodass sie die Codeausführung anhalten.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-147">Enables all breakpoints so that they stop code execution.</span></span> <span data-ttu-id="a8d1a-148">Wenn alle Breakpoints aktiviert sind, wird diese Schaltfläche als **Alle Breakpoints deaktivieren**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-148">When all breakpoints are enabled, this button becomes **Disable All Breakpoints**.</span></span>  
  
 <span data-ttu-id="a8d1a-149">**Gehe zu Quellcode**</span><span class="sxs-lookup"><span data-stu-id="a8d1a-149">**Go To Source Code**</span></span>  
 <span data-ttu-id="a8d1a-150">Positioniert den Cursor im Abfrage-Editor auf der Zeile, die den ausgewählten Breakpoint enthält.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-150">Positions the cursor on the line in the Query Editor that contains the selected breakpoint.</span></span>  
  
 <span data-ttu-id="a8d1a-151">**Spalten**</span><span class="sxs-lookup"><span data-stu-id="a8d1a-151">**Columns**</span></span>  
 <span data-ttu-id="a8d1a-152">Listet alle Spalten auf, die im Fenster **Breakpoints** angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-152">Lists all the columns that can be displayed in the **Breakpoints** window.</span></span> <span data-ttu-id="a8d1a-153">Ein Kontrollkästchen gibt die Spalten an, die angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-153">A check box indicates the columns that are displayed.</span></span> <span data-ttu-id="a8d1a-154">Um eine Spalte im Fenster **Breakpoints** hinzuzufügen oder zu entfernen, wählen Sie die Spalte in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="a8d1a-154">To add or remove a column in the **Breakpoints** window, select the column on the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8d1a-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a8d1a-155">See Also</span></span>  
 [<span data-ttu-id="a8d1a-156">Transact-SQL-Debugger</span><span class="sxs-lookup"><span data-stu-id="a8d1a-156">Transact-SQL Debugger</span></span>](transact-sql-debugger.md)  
