---
title: Überwachung (Fenster)
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Watch Window [Transact-SQL]
ms.assetid: 23f3baa4-14c2-4262-92f7-3f43fcfa0436
author: rothja
ms.author: jroth
ms.openlocfilehash: c2a3db9b095902fcb5620af91fb86d80f773d606
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620260"
---
# <a name="watch-window"></a><span data-ttu-id="7d7e2-102">Überwachung (Fenster)</span><span class="sxs-lookup"><span data-stu-id="7d7e2-102">Watch Window</span></span>
  <span data-ttu-id="7d7e2-103">Im Fenster **Überwachung** werden Informationen über die Ausdrücke angezeigt, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-103">The **Watch** window displays information about the expressions that you have selected.</span></span> <span data-ttu-id="7d7e2-104">Es können bis zu vier Überwachungsfenster verfügbar sein: **Überwachen 1**, **Überwachen 2**, Überwachen 3 und **Überwachen 4**.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-104">There can be up to four watch windows: **Watch 1**, **Watch 2, Watch 3**, and **Watch 4**.</span></span> <span data-ttu-id="7d7e2-105">Die Ausdrücke werden innerhalb des Bereichs des aktuellen Aufruflistenrahmens ausgewertet, der im Fenster **Aufrufliste** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-105">The expressions are evaluated within the scope of the current call stack frame that is selected in the **Call Stack** window.</span></span> <span data-ttu-id="7d7e2-106">Sie müssen sich im Debugmodus befinden, um Variablen und Ausdrücke zu beobachten.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-106">You must be in debug mode to watch variables and expressions.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="7d7e2-107">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="7d7e2-107">Task List</span></span>  
 <span data-ttu-id="7d7e2-108">**So greifen Sie auf die Überwachungsfenster zu**</span><span class="sxs-lookup"><span data-stu-id="7d7e2-108">**To access the Watch windows**</span></span>  
  
-   <span data-ttu-id="7d7e2-109">Klicken Sie im Menü **Debuggen** auf **Fenster**, klicken Sie auf **Überwachung**, und klicken Sie dann auf **Überwachung 1**, **Überwachung 2**, **Überwachung 3**oder Überwachung 4.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-109">On the **Debug** menu, click **Windows**, click **Watch**, and then click **Watch 1**, **Watch 2, Watch 3**, or **Watch 4**.</span></span>  
  
 <span data-ttu-id="7d7e2-110">**So ändern Sie den Wert eines Ausdrucks**</span><span class="sxs-lookup"><span data-stu-id="7d7e2-110">**To change the value of an expression**</span></span>  
  
-   <span data-ttu-id="7d7e2-111">Klicken mit der rechten Maustaste auf den Ausdruck, und wählen Sie anschließend **Wert bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-111">Right-click the expression, and then select **Edit Value**.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="7d7e2-112">Spalten</span><span class="sxs-lookup"><span data-stu-id="7d7e2-112">Columns</span></span>  
 <span data-ttu-id="7d7e2-113">**Name**</span><span class="sxs-lookup"><span data-stu-id="7d7e2-113">**Name**</span></span>  
 <span data-ttu-id="7d7e2-114">Die Ausdrücke, die vom [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-114">Are the expressions that are listed by the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger.</span></span> <span data-ttu-id="7d7e2-115">Die folgenden Ausdrücke werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7d7e2-115">The following expressions are supported:</span></span>  
  
-   <span data-ttu-id="7d7e2-116">Variablen</span><span class="sxs-lookup"><span data-stu-id="7d7e2-116">Variables.</span></span>  
  
-   <span data-ttu-id="7d7e2-117">Parameter.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-117">Parameters.</span></span>  
  
-   <span data-ttu-id="7d7e2-118">Systemfunktionen, deren Name mit „@@“ beginnt.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-118">System functions whose name starts with @@.</span></span>  
  
-   <span data-ttu-id="7d7e2-119">Ausdrücke, die durch Anwenden von Operatoren auf eine oder mehrere Variablen, Parameter oder Systemfunktionen erstellt werden, z.B. "@IntegerCounter + 1" oder "FirstName + LastName"</span><span class="sxs-lookup"><span data-stu-id="7d7e2-119">Expressions built by applying operators to one or more variables, parameters, or system functions, such as @IntegerCounter + 1, or FirstName + LastName.</span></span>  
  
-   <span data-ttu-id="7d7e2-120">Transact-SQL-Anweisungen, die einen einzelnen Wert zurückgeben, z. B.: "SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1"</span><span class="sxs-lookup"><span data-stu-id="7d7e2-120">Transact-SQL statements that return a single value, such as: SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span></span>  
  
 <span data-ttu-id="7d7e2-121">**Wert**</span><span class="sxs-lookup"><span data-stu-id="7d7e2-121">**Value**</span></span>  
 <span data-ttu-id="7d7e2-122">Zeigt den Wert an, der zurückgegeben wird, nachdem der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger den in **Name**angegebenen Ausdruck ausgewertet hat.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-122">Displays the value that is returned after the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger evaluates the expression specified in **Name**.</span></span>  
  
 <span data-ttu-id="7d7e2-123">Wenn die Länge eines Ausdrucks größer als die Breite der Spalte **Wert** ist, wird der vollständige Wert in einer QuickInfo angezeigt, wenn Sie den Mauszeiger über die **Wertzelle** für diesen Ausdruck bewegen.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-123">If the length of an expression is larger than the width of the **Value** column, a tooltip displays the full value when you move the pointer over the **Value** cell for that expression.</span></span>  
  
 <span data-ttu-id="7d7e2-124">Ein Lupensymbol in einer **Wertzelle** zeigt an, dass die [!INCLUDE[tsql](../../includes/tsql-md.md)] Debuggerschnellansicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-124">A magnifying glass icon in a **Value** cell indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger visualizer is available.</span></span> <span data-ttu-id="7d7e2-125">In der Liste können Sie **Text-Schnellansicht**, **XML-Schnellansicht**oder **HTML-Schnellansicht**angeben.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-125">In the list, you can specify **Text Visualizer**, **XML Visualizer**, or **HTML Visualizer**.</span></span> <span data-ttu-id="7d7e2-126">Um eine Debuggerschnellansicht zu starten, klicken Sie auf das Lupensymbol.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-126">To start a debugger visualizer, click the magnifying glass icon.</span></span> <span data-ttu-id="7d7e2-127">Der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger öffnet ein Dialogfeld, in dem die Daten in einem für den Datentyp geeigneten Format angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-127">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger opens a dialog that displays the data in a format appropriate to the data type.</span></span>  
  
 <span data-ttu-id="7d7e2-128">**Typ**</span><span class="sxs-lookup"><span data-stu-id="7d7e2-128">**Type**</span></span>  
 <span data-ttu-id="7d7e2-129">Zeigt den Datentyp des Ausdrucks an.</span><span class="sxs-lookup"><span data-stu-id="7d7e2-129">Displays the data type of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d7e2-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d7e2-130">See Also</span></span>  
 <span data-ttu-id="7d7e2-131">[Transact-SQL-Debugger](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="7d7e2-131">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="7d7e2-132">[Transact-SQL-Debuggerinformationen](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="7d7e2-132">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="7d7e2-133">[Lokal (Fenster)](transact-sql-debugger-locals-window.md) </span><span class="sxs-lookup"><span data-stu-id="7d7e2-133">[Locals Window](transact-sql-debugger-locals-window.md) </span></span>  
 <span data-ttu-id="7d7e2-134">[Fenster 'Aufrufliste'](transact-sql-debugger-call-stack-window.md) </span><span class="sxs-lookup"><span data-stu-id="7d7e2-134">[Call Stack Window](transact-sql-debugger-call-stack-window.md) </span></span>  
 <span data-ttu-id="7d7e2-135">[Dialogfeld 'Schnellüberwachung'](transact-sql-debugger-quickwatch-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="7d7e2-135">[QuickWatch Dialog Box](transact-sql-debugger-quickwatch-dialog-box.md) </span></span>  
 [<span data-ttu-id="7d7e2-136">Ausdrücke &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7d7e2-136">Expressions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/expressions-transact-sql)  
