---
title: Lokal (Fenster)
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Locals Window [Transact-SQL]
ms.assetid: 59bea640-7823-4b4d-832c-f384d83cca2f
author: rothja
ms.author: jroth
ms.openlocfilehash: 6f8f62eb69a50d7543af41dddb9c62c842d17151
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622002"
---
# <a name="locals-window"></a><span data-ttu-id="c490d-102">Lokalfenster</span><span class="sxs-lookup"><span data-stu-id="c490d-102">Locals Window</span></span>
  <span data-ttu-id="c490d-103">Im Fenster **Lokal** werden Informationen über die lokalen Ausdrücke im aktuellen Bereich des [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debuggers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c490d-103">The **Locals** window displays information about the local expressions in the current scope of the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger.</span></span> <span data-ttu-id="c490d-104">Der Bereich wird auf den aktuellen Aufruflistenrahmen festgelegt, der im Fenster **Aufrufliste** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="c490d-104">The scope is set to the current call stack frame that is selected in the **Call Stack** window.</span></span> <span data-ttu-id="c490d-105">Sie müssen sich im Debugmodus befinden, um die lokalen Ausdrücke anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c490d-105">You must be in debug mode to display the local expressions.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="c490d-106">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="c490d-106">Task List</span></span>  
 <span data-ttu-id="c490d-107">**So greifen Sie auf das Fenster Lokal zu**</span><span class="sxs-lookup"><span data-stu-id="c490d-107">**To access the Locals window**</span></span>  
  
-   <span data-ttu-id="c490d-108">Klicken Sie im Menü **Debuggen** auf **Fenster**, und klicken Sie dann auf **Lokal**.</span><span class="sxs-lookup"><span data-stu-id="c490d-108">On the **Debug** menu, click **Windows**, and then click **Locals**.</span></span>  
  
 <span data-ttu-id="c490d-109">**So ändern Sie den Wert eines Ausdrucks**</span><span class="sxs-lookup"><span data-stu-id="c490d-109">**To change the value of an expression**</span></span>  
  
-   <span data-ttu-id="c490d-110">Klicken mit der rechten Maustaste auf den Ausdruck, und wählen Sie anschließend **Wert bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="c490d-110">Right-click the expression, and then select **Edit Value**.</span></span>  
  
## <a name="columns"></a><span data-ttu-id="c490d-111">Spalten</span><span class="sxs-lookup"><span data-stu-id="c490d-111">Columns</span></span>  
 <span data-ttu-id="c490d-112">**Name**</span><span class="sxs-lookup"><span data-stu-id="c490d-112">**Name**</span></span>  
 <span data-ttu-id="c490d-113">Der Name des lokalen Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="c490d-113">Is the name of the local expression.</span></span> <span data-ttu-id="c490d-114">Der [!INCLUDE[tsql](../../includes/tsql-md.md)]-Debugger führt Variablen, Parameter und die Systemfunktionen, deren Namen mit @@ beginnen, auf.</span><span class="sxs-lookup"><span data-stu-id="c490d-114">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger lists variables, parameters, and the system functions that have names that start with @@.</span></span>  
  
 <span data-ttu-id="c490d-115">**Wert**</span><span class="sxs-lookup"><span data-stu-id="c490d-115">**Value**</span></span>  
 <span data-ttu-id="c490d-116">Zeigt den Wert an, der dem lokalen Ausdruck derzeit zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="c490d-116">Displays the value that is currently assigned to the local expression.</span></span> <span data-ttu-id="c490d-117">Diese Spalte ist leer, wenn dem Ausdruck kein Wert zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="c490d-117">This column is blank when no value has been assigned to the expression.</span></span>  
  
 <span data-ttu-id="c490d-118">Wenn die Länge eines Ausdrucks größer als die Breite der Spalte **Wert** ist, wird der vollständige Wert in einer QuickInfo angezeigt, wenn Sie den Mauszeiger über die **Wertzelle** für diesen Ausdruck bewegen.</span><span class="sxs-lookup"><span data-stu-id="c490d-118">If the length of an expression is larger than the width of the **Value** column, a tooltip displays the full value when you move the pointer over the **Value** cell for that expression.</span></span>  
  
 <span data-ttu-id="c490d-119">Ein Lupensymbol in einer **Wertzelle** zeigt an, dass die [!INCLUDE[tsql](../../includes/tsql-md.md)] Debuggerschnellansicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c490d-119">A magnifying glass icon in a **Value** cell indicates that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger visualizer is available.</span></span> <span data-ttu-id="c490d-120">In der Liste können Sie **Text-Schnellansicht**, **XML-Schnellansicht**oder **HTML-Schnellansicht**angeben.</span><span class="sxs-lookup"><span data-stu-id="c490d-120">In the list, you can specify **Text Visualizer**, **XML Visualizer**, or **HTML Visualizer**.</span></span> <span data-ttu-id="c490d-121">Um eine Debuggerschnellansicht zu starten, klicken Sie auf das Lupensymbol.</span><span class="sxs-lookup"><span data-stu-id="c490d-121">To start a debugger visualizer, click the magnifying glass icon.</span></span> <span data-ttu-id="c490d-122">Der [!INCLUDE[tsql](../../includes/tsql-md.md)] -Debugger öffnet ein Dialogfeld, in dem die Daten in einem für den Datentyp geeigneten Format angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c490d-122">The [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger opens a dialog box that displays the data in a format appropriate to the data type.</span></span>  
  
 <span data-ttu-id="c490d-123">**Typ**</span><span class="sxs-lookup"><span data-stu-id="c490d-123">**Type**</span></span>  
 <span data-ttu-id="c490d-124">Zeigt den Datentyp des Ausdrucks an.</span><span class="sxs-lookup"><span data-stu-id="c490d-124">Displays the data type of the expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c490d-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c490d-125">See Also</span></span>  
 <span data-ttu-id="c490d-126">[Transact-SQL-Debugger](transact-sql-debugger.md) </span><span class="sxs-lookup"><span data-stu-id="c490d-126">[Transact-SQL Debugger](transact-sql-debugger.md) </span></span>  
 <span data-ttu-id="c490d-127">[Transact-SQL-Debuggerinformationen](transact-sql-debugger-information.md) </span><span class="sxs-lookup"><span data-stu-id="c490d-127">[Transact-SQL Debugger Information](transact-sql-debugger-information.md) </span></span>  
 <span data-ttu-id="c490d-128">[Überwachung (Fenster)](transact-sql-debugger-watch-window.md) </span><span class="sxs-lookup"><span data-stu-id="c490d-128">[Watch Window](transact-sql-debugger-watch-window.md) </span></span>  
 <span data-ttu-id="c490d-129">[Fenster 'Aufrufliste'](transact-sql-debugger-call-stack-window.md) </span><span class="sxs-lookup"><span data-stu-id="c490d-129">[Call Stack Window](transact-sql-debugger-call-stack-window.md) </span></span>  
 <span data-ttu-id="c490d-130">[Dialogfeld 'Schnellüberwachung'](transact-sql-debugger-quickwatch-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="c490d-130">[QuickWatch Dialog Box](transact-sql-debugger-quickwatch-dialog-box.md) </span></span>  
 [<span data-ttu-id="c490d-131">Ausdrücke &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c490d-131">Expressions &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/expressions-transact-sql)  
