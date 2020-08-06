---
title: Dialogfeld 'Schnellüberwachung'
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- vs.debug.quickwatch
helpviewer_keywords:
- QuickWatch Dialog [Transact-SQL]
ms.assetid: d6bbb373-1452-41f2-bdc5-86ae689c3dc0
author: rothja
ms.author: jroth
ms.openlocfilehash: 48e4bda558b75bec0c81815c90feff9d6500a803
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622000"
---
# <a name="quickwatch-dialog-box"></a><span data-ttu-id="bf0ca-102">Dialogfeld 'Schnellüberwachung'</span><span class="sxs-lookup"><span data-stu-id="bf0ca-102">QuickWatch Dialog Box</span></span>
  <span data-ttu-id="bf0ca-103">Mithilfe des Dialogfelds **Schnellüberwachung** können Sie beim Debuggen von [!INCLUDE[tsql](../../includes/tsql-md.md)] -Code schnell den Datentyp und den Wert eines [!INCLUDE[tsql](../../includes/tsql-md.md)] -Ausdrucks anzeigen, wie z. B. einer Variable oder eines Parameters.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-103">Use the **QuickWatch** dialog box to quickly view the data type and value of one [!INCLUDE[tsql](../../includes/tsql-md.md)] expression, such as a variable or parameter, when you are debugging [!INCLUDE[tsql](../../includes/tsql-md.md)] code.</span></span> <span data-ttu-id="bf0ca-104">Um mehrere Ausdrücke zu beobachten, können Sie den Ausdruck auch einem **Überwachungsfenster** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-104">To watch multiple expressions, you can also add the expression to a **Watch** window.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="bf0ca-105">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="bf0ca-105">Task List</span></span>  
 <span data-ttu-id="bf0ca-106">**So greifen Sie auf das Dialogfeld Schnellüberwachung zu**</span><span class="sxs-lookup"><span data-stu-id="bf0ca-106">**To access the QuickWatch dialog box**</span></span>  
  
-   <span data-ttu-id="bf0ca-107">Klicken Sie im Menü **Debuggen** auf **Schnellüberwachung**.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-107">On the **Debug** menu, click **QuickWatch**.</span></span>  
  
 <span data-ttu-id="bf0ca-108">**So zeigen Sie die Informationen zu einem Ausdruck an**</span><span class="sxs-lookup"><span data-stu-id="bf0ca-108">**To view the information about an expression**</span></span>  
  
1.  <span data-ttu-id="bf0ca-109">Geben Sie den gewünschten Ausdruck im Listenfeld **Ausdruck** ein, oder wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-109">In the **Expression** list box, type or select the expression that you want.</span></span> <span data-ttu-id="bf0ca-110">Die folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Ausdrücke werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="bf0ca-110">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] expressions are supported:</span></span>  
  
    -   <span data-ttu-id="bf0ca-111">Variablen</span><span class="sxs-lookup"><span data-stu-id="bf0ca-111">Variables.</span></span>  
  
    -   <span data-ttu-id="bf0ca-112">Parameter.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-112">Parameters.</span></span>  
  
    -   <span data-ttu-id="bf0ca-113">Systemfunktionen, deren Name mit „@@“ beginnt.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-113">System functions whose name starts with @@.</span></span>  
  
    -   <span data-ttu-id="bf0ca-114">Ausdrücke, die durch Anwenden von Operatoren auf eine oder mehrere Variablen, Parameter oder Systemfunktionen erstellt werden, z.B. "@IntegerCounter + 1" oder "FirstName + LastName"</span><span class="sxs-lookup"><span data-stu-id="bf0ca-114">Expressions built by applying operators to one or more variables, parameters, or system functions, such as @IntegerCounter + 1, or FirstName + LastName.</span></span>  
  
    -   <span data-ttu-id="bf0ca-115">Transact-SQL-Anweisungen, die einen einzelnen Wert zurückgeben, z. B.: "SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1"</span><span class="sxs-lookup"><span data-stu-id="bf0ca-115">Transact-SQL statements that return a single value, such as: SELECT CharacterCol FROM MyTable WHERE PrimaryKey = 1.</span></span>  
  
2.  <span data-ttu-id="bf0ca-116">Klicken Sie auf **Neu auswerten**.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-116">Click **Reevaluate**.</span></span>  
  
 <span data-ttu-id="bf0ca-117">**So fügen Sie den Ausdruck der Schnellüberwachung einem Überwachungsfenster hinzu**</span><span class="sxs-lookup"><span data-stu-id="bf0ca-117">**To add the QuickWatch expression to a Watch window**</span></span>  
  
-   <span data-ttu-id="bf0ca-118">Klicken Sie auf **Überwachung hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-118">Click **Add Watch**.</span></span>  
  
 <span data-ttu-id="bf0ca-119">**So ändern Sie den Wert des Ausdrucks der Schnellüberwachung**</span><span class="sxs-lookup"><span data-stu-id="bf0ca-119">**To change the value of the QuickWatch expression**</span></span>  
  
-   <span data-ttu-id="bf0ca-120">Klicken mit der rechten Maustaste auf den Ausdruck, und wählen Sie anschließend **Wert bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-120">Right-click the expression, and then select **Edit Value**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bf0ca-121">Tastatur</span><span class="sxs-lookup"><span data-stu-id="bf0ca-121">Options</span></span>  
 <span data-ttu-id="bf0ca-122">**Ausdruckliste**</span><span class="sxs-lookup"><span data-stu-id="bf0ca-122">**Expression list**</span></span>  
 <span data-ttu-id="bf0ca-123">Zeigt den aktuell ausgewählten Ausdruck an.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-123">Displays the currently selected expression.</span></span> <span data-ttu-id="bf0ca-124">Die Dropdownliste enthält einen Satz von Ausdrücken, deren Anzeige Sie auswählen können.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-124">The drop-down list contains a set of expressions that you can select to display.</span></span> <span data-ttu-id="bf0ca-125">In der Liste sind jene Ausdrücke aufgeführt, die im Bereich des Stapelrahmens verfügbar sind, der im Fenster **Aufrufliste** aktuell ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-125">The expressions in the list are those available in the scope of the stack frame that is currently selected in the **Call Stack** window.</span></span> <span data-ttu-id="bf0ca-126">Um einen anderen Ausdruck anzuzeigen, geben Sie entweder den Ausdruck ein, oder wählen Sie ihn aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-126">To display a different expression, either enter the expression or select it from list.</span></span> <span data-ttu-id="bf0ca-127">Der [!INCLUDE[tsql](../../includes/tsql-md.md)]-Debugger unterstützt die folgenden Ausdrücke: Variablen, Parameter und die Systemfunktionen, deren Namen mit @@ beginnen.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-127">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger supports the following expressions: variables, parameters, and the system functions that have names that start with @@.</span></span>  
  
 <span data-ttu-id="bf0ca-128">**Werteraster**</span><span class="sxs-lookup"><span data-stu-id="bf0ca-128">**Value grid**</span></span>  
 <span data-ttu-id="bf0ca-129">Zeigt die Eigenschaften des Ausdrucks an, der gerade beobachtet wird.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-129">Displays the properties of the expression that is currently being watched.</span></span>  
  
 <span data-ttu-id="bf0ca-130">**Name**</span><span class="sxs-lookup"><span data-stu-id="bf0ca-130">**Name**</span></span>  
 <span data-ttu-id="bf0ca-131">Entspricht dem [!INCLUDE[tsql](../../includes/tsql-md.md)] -Ausdruck, der beobachtet wird.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-131">Is the [!INCLUDE[tsql](../../includes/tsql-md.md)] expression being watched.</span></span>  
  
 <span data-ttu-id="bf0ca-132">**Wert**</span><span class="sxs-lookup"><span data-stu-id="bf0ca-132">**Value**</span></span>  
 <span data-ttu-id="bf0ca-133">Zeigt den Wert an, der dem Ausdruck derzeit zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-133">Displays the value that is currently assigned to the expression.</span></span> <span data-ttu-id="bf0ca-134">Ein Leerzeichen wird angezeigt, wenn der Ausdruck gerade über keinen Wert verfügt.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-134">A blank is displayed when the expression currently has no value.</span></span>  
  
 <span data-ttu-id="bf0ca-135">Wenn die Länge eines Ausdrucks größer als die Breite der Spalte **Wert** ist, wird der vollständige Wert in einer QuickInfo angezeigt, wenn Sie den Mauszeiger über die **Wertzelle** für diesen Ausdruck bewegen.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-135">If the length of an expression is larger than the width of the **Value** column, a tooltip displays the full value when you move the pointer over the **Value** cell for that expression.</span></span>  
  
 <span data-ttu-id="bf0ca-136">Ein Lupensymbol in einer **Wertzelle** zeigt an, dass die [!INCLUDE[tsql](../../includes/tsql-md.md)] Debuggerschnellansicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-136">A magnifying glass icon in a **Value** cell indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger visualizer is available.</span></span> <span data-ttu-id="bf0ca-137">In der Liste können Sie **Text-Schnellansicht**, **XML-Schnellansicht**oder **HTML-Schnellansicht**angeben.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-137">In the list, you can specify **Text Visualizer**, **XML Visualizer**, or **HTML Visualizer**.</span></span> <span data-ttu-id="bf0ca-138">Um eine Debuggerschnellansicht zu starten, klicken Sie auf das Lupensymbol.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-138">To start a debugger visualizer, click the magnifying glass icon.</span></span> <span data-ttu-id="bf0ca-139">Der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger öffnet ein Dialogfeld, in dem die Daten in einem für den Datentyp geeigneten Format angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-139">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger opens a dialog box that displays the data in a format appropriate to the data type.</span></span>  
  
 <span data-ttu-id="bf0ca-140">**Typ**</span><span class="sxs-lookup"><span data-stu-id="bf0ca-140">**Type**</span></span>  
 <span data-ttu-id="bf0ca-141">Zeigt den Datentyp des Ausdrucks an.</span><span class="sxs-lookup"><span data-stu-id="bf0ca-141">Displays the data type of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf0ca-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bf0ca-142">See Also</span></span>  
 <span data-ttu-id="bf0ca-143">[Transact-SQL-Debugger](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="bf0ca-143">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="bf0ca-144">[Transact-SQL-Debuggerinformationen](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="bf0ca-144">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="bf0ca-145">[Überwachung (Fenster)](transact-sql-debugger-watch-window.md) </span><span class="sxs-lookup"><span data-stu-id="bf0ca-145">[Watch Window](transact-sql-debugger-watch-window.md) </span></span>  
 <span data-ttu-id="bf0ca-146">[Lokal (Fenster)](transact-sql-debugger-locals-window.md) </span><span class="sxs-lookup"><span data-stu-id="bf0ca-146">[Locals Window](transact-sql-debugger-locals-window.md) </span></span>  
 <span data-ttu-id="bf0ca-147">[Fenster 'Aufrufliste'](transact-sql-debugger-call-stack-window.md) </span><span class="sxs-lookup"><span data-stu-id="bf0ca-147">[Call Stack Window](transact-sql-debugger-call-stack-window.md) </span></span>  
 [<span data-ttu-id="bf0ca-148">Ausdrücke &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bf0ca-148">Expressions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/expressions-transact-sql)  
  
  
